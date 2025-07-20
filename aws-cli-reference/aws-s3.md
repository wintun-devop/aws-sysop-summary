### AWS S3 Official CLI(https://docs.aws.amazon.com/cli/v1/userguide/cli-services-s3-commands.html)
- High Leve
```
aws s3 ls
```
- delete objects in bucket in case of no versioning enable
```
aws s3 rm s3://your-bucket-name --recursive
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
### Deleteing s3 bucket
- In case of versioning is enabled, we must delete all versions and delete markers:
```
aws s3api delete-objects \
  --bucket your-bucket-name \
  --delete "$(aws s3api list-object-versions \
    --bucket your-bucket-name \
    --output=json \
    --query='{Objects: Versions[].{Key:Key,VersionId:VersionId}}')"
```
```
aws s3api delete-objects \
  --bucket your-bucket-name \
  --delete "$(aws s3api list-object-versions \
    --bucket your-bucket-name \
    --output=json \
    --query='{Objects: DeleteMarkers[].{Key:Key,VersionId:VersionId}}')"
```
- Delete the bucket
```
aws s3api delete-bucket \
  --bucket your-bucket-name \
  --region ap-southeast-1  
```


