## Create a bucket using s3api
```sh 
aws s3api create-bucket --bucket matleza-acl
```

## Turn of Block Public Access for ACLs
```sh
aws s3api put-public-access-block \
--bucket matleza-acl \ --public-access-block-configuration "BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=true,RestrictPublicBuckets=true"
```

## Get public access block
```sh
aws s3api get-public-access-block --bucket matleza-acl
```

## Update the bucket onwership settings of a bucket
```sh
aws s3api put-bucket-ownership-controls \
--bucket matleza-acl \
--ownership-controls="Rules=[{ObjectOwnership=BucketOwnerPreferred}]"
```

## To retrieve the bucket ownership settings of a bucket
```sh
aws s3api get-bucket-ownership-controls --bucket matleza-acl
```

## Change acls to allow for a user in another aws account
```sh
aws s3api put-bucket-acl --bucket matleza-acl --grant-full-control emailaddress=katlehomokhethi1@gmail.com --grant-read uri=http://acs.amazonaws.com/groups/global/AllUsers
```

## Access Bucket from other account 
```sh
touch bootcamp.txt
aws s3 cp bootcamp.txt s3://matleza-acl
aws ls s3://matleza-acl
```

## Cleanup Resources
```sh 
aws s3 rm s3://matleza-acl/bootcamp.txt
aws s3 rb s3://matleza-acl
```