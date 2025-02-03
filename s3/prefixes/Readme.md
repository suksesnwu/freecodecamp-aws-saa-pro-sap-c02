## Create our bucket
```sh
aws s3 mb s3://prefixes-matleza
```
## Create our folder
```sh
aws s3api put-object --bucket="prefixes-matleza" --key="hello/"
```

## Create many folders
```sh
aws s3api put-object --bucket="prefixes-matleza" --key="hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/hello/"
```