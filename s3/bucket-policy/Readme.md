## Create a bucket using s3api
```sh 
aws s3api create-bucket --bucket matleza-bucket-policy
```

## Create a bucket policy
```sh
aws s3api put-bucket-policy --bucket matleza-bucket-policy --policy file:///workspaces/freecodecamp-aws-saa-pro-sap-c02/s3/bucket-policy/policy.json
```

## In the other account access the bucket
```sh
touch bootcamp.txt
aws s3 cp bootcamp.txt s3://matleza-bucket-policy
aws s3 ls s3://matleza-bucket-policy
```

## Cleanup Resources
```sh
aws s3 rm s3://matleza-bucket-policy/bootcamp.txt
aws s3 rb s3://matleza-bucket-policy
```
