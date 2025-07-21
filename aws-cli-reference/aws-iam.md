### Official AWS CLI Documentation for IAM (https://docs.aws.amazon.com/cli/latest/reference/iam/)
- to check credentials setup 
```
aws sts get-caller-identity
```
- to check credentials setup in specific account profile
```
AWS_PROFILE=dev AWS_DEFAULT_OUTPUT=table AWS_DEFAULT_REGION=us-east-1 aws sts get-caller-identity
```

### External Reference 
 - https://dynobase.dev/dynamodb-cli-query-examples/
   
