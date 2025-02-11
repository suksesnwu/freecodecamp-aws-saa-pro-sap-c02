## Create a bucket

```sh
aws s3 mb s3://matleza-endpoint-test
```

## Upload a file to s3 using standard output
```sh
touch standard.txt
aws s3 cp standard.txt s3://matleza-endpoint-test --endpoint-url https://s3.us-east-1.amazonaws.com
```

## Upload a file to s3 using dualstack endpoint
```sh
touch dualstack.txt
aws s3 cp dualstack.txt s3://matleza-endpoint-test --endpoint-url https://s3.dualstack.us-east-1.amazonaws.com
```

## Cleanup
```sh
aws s3 rm s3://matleza-endpoint-test/standard.txt
aws s3 rm s3://matleza-endpoint-test/dualstack.txt
aws s3 rb s3://matleza-endpoint-test
```