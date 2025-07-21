### Official AWS CLI Documentation for IAM (https://docs.aws.amazon.com/cli/latest/reference/iam/)
- to check credentials setup 
```
aws sts get-caller-identity
```
- to check credentials setup in specific account profile
```
AWS_PROFILE=dev AWS_DEFAULT_OUTPUT=table AWS_DEFAULT_REGION=us-east-1 aws sts get-caller-identity
```
- create policy
```
aws iam create-policy \
    --policy-name DynamoDBManagementPolicy \
    --policy-document '{
        "Version": "2024-05-25",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "dynamodb:CreateTable",
                    "dynamodb:PutItem",
                    "dynamodb:GetItem",
                    "dynamodb:Query",
                    "dynamodb:UpdateItem",
                    "dynamodb:DeleteItem",
                    "dynamodb:DeleteTable"
                ],
                "Resource": "*"
            }
        ]
    }'
```

### External Reference 
 - https://dynobase.dev/dynamodb-cli-query-examples/
   
