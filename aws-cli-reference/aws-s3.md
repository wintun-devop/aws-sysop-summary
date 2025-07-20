### AWS S3 Official CLI(https://docs.aws.amazon.com/cli/v1/userguide/cli-services-s3-commands.html)
- High Leve
```
aws s3 ls
```

- API Level
	- create backup for home region(us-east-1)
```
aws s3api create-bucket \
  --bucket your_backup_name \
  --region us-east-1
```
	- create backup for out of home region
```
aws s3api create-bucket \
  --bucket yoour_backup_name \
  --region ap-southeast-1 \
  --create-bucket-configuration LocationConstraint=ap-southeast-1

```
	- version enable
```
aws s3api put-bucket-versioning \
  --bucket my-terraform-state-bucket \
  --versioning-configuration Status=Enabled
```


