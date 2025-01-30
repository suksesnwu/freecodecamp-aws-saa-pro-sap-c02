## Create a new s3 bucket
```
aws s3 mb s3://checksums-matleza
```

## Create a file that will we do a checksum on

```
echo "This phrase on the first line" > myfile.txt
```

## Get a checksum of a file for md5

```md
md5sum myfile.txt
# 8a091dd02629ea5f455e959a23633f82 *myfile.txt
```

## Upload our file to the bucket
```
aws s3 cp myfile.txt s3://checksums-matleza
aws s3api head-object --bucket checksums-matleza --key myfile.txt
```

## Let's upload a file using a different kind of checksum

```sh
bundle exec ruby crc.rb
```

```sh
aws s3api put-object \
--bucket checksums-matleza \
--key="myfilecrc32.txt" \
--body=myfile.txt" \
--checksum-algorithm="CRC32" \
--checksum-crc32="4027661802"
```

