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

## Create a new file
```sh
echo "This is a governance object lock file" > object-lock.txt
```

## Copying a local file to S3
```sh
aws s3 cp object-lock.txt s3://matleza-object-lock
```

## delete the file
```sh
aws s3 rm s3://matleza-object-lock/legal.txt
```

## Retrieve an object lock configuration for a bucket
```sh
aws s3api get-object-lock-configuration \
--bucket matleza-object-lock
```

## delete the versioned file
```sh
aws s3api delete-bucket --bucket matleza-object-lock --key "gov.txt" --version-id=" " --bypass-governance-retention
```

## use compliance mode s3 object
```sh
aws s3api put-object --bucket matleza-object-lock --key "gov.txt" --body="compliance.txt" --object-lock-mode COMPLIANCE --object-lock-retain-until-date="2023-12-16R00:00:02"
```

## try and delete specific version
```sh
aws s3api delete-bucket --bucket matleza-object-lock --key "gov.txt" --version-id=" " 
```

## Create a new file
```sh
echo "This is a legal text file" > legal.txt
```

## Copying a local file to S3
```sh
aws s3 cp legal.txt s3://matleza-object-lock
```

## Legal Holds

```sh
aws s3api put-object-legal-hold --bucket "matleza-object-lock" --key legal.txt --legal-hold Status=ON
```

```sh
aws s3api rm s3://matleza-object-lock/legal.txt
```

```sh
aws s3api list-objects-versions --bucket matleza-object-lock
```

```sh
aws s3api list--versions --bucket matleza-object-lock
```

```sh
aws s3api delete-object --bucket matleza-object-lock --key "legal.txt" version-id=" "
```

```sh
aws s3api put-object-legal-hold --bucket matleza-object-lock --version-id=" " --key "legal.txt" --legal-hold Status=OFF
```

```sh
aws s3api delete-object --bucket matleza-object-lock --key "legal.txt" version-id=" " --bypass-governance-retention
```

## Create a new bucket
```sh
aws s3 mb s3://matleza-object-lock
```