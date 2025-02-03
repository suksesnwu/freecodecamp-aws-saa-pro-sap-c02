## Create a bucket
```sh
aws s3 mb s3://metadata-matleza
```
## Create a new file
```sh
echo "Hello Mars" > hello.txt
```

## Upload file with metadata
```sh
aws s3api put-object --bucket="metadata-matleza" --key hello.txt --body hello.txt --metadata Planet=Mars
```

## Get metadata through head object
```sh
aws s3api head-object --bucket "metadata-matleza" --key hello.txt 
```