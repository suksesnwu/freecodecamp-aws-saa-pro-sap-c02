## Create a bucket
```sh
aws s3 mb s3://matleza-cors
```

## Changec a block public accress
```sh
aws s3api put-public-access-block \
--bucket matleza-cors \
--public-access-block-configuration "BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=false,RestrictPublicBuckets=false"
```

## Create a bucket policy
```sh
aws s3api put-bucket-policy --bucket matleza-cors --policy file:///cors-policy.json
```

## Turn on static website hosting
```sh
aws s3api 
```

## upload our index.html file and include a resouce that would be origin
```sh
aws s3api 
```

## Apply a CORS policy
```sh
aws s3api 
```

## 
```sh
aws s3api 
```
