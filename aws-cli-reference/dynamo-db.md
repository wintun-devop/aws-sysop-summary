### DynamoDB Official Docs(https://docs.aws.amazon.com/cli/latest/reference/dynamodb/)
- Create Table
```
aws dynamodb create-table \
  --table-name terraform-locks \
  --attribute-definitions AttributeName=LockID,AttributeType=S \
  --key-schema AttributeName=LockID,KeyType=HASH \
  --billing-mode PAY_PER_REQUEST
```
