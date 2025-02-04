## Create a new bucket
```sh
aws s3 mb s3://matleza-object-lock
```

## Turn on versioning
```sh
aws s3api put-bucket-versioning --bucket matleza-object-lock --versioning-configuration Status=Enabled
```

## Turn on Object Locking
```sh
aws s3api put-object-lock-configuration \
--bucket matleza-object-lock \
--object-lock-configuration '{ "ObjectLockEnabled": "Enabled", "Rule": { "DefaultRetention": { "Mode": "GOVERNANCE", "Days": 1 }}}'
```

## Retrieve an object lock configuration for a bucket
```sh
aws s3api get-object-lock-configuration \
--bucket matleza-object-lock
```
