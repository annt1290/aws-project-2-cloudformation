# Udacity AWS Devops - Project 2 CloudFormation

Deploy a high-availability web app using CloudFormation

## Resources

1. [Diagram](diagram.png)
2. [Infra template](infra.yml)
3. [Infra parameters](infra-parameters.json)
4. [Servers template](servers.yml)
5. [Servers parameters](servers-parameters.json)
6. [Web app](web-app)

## Result

- Load balancer URL: http://proje-loadb-1bgxvd8xgj8q4-349680280.us-east-1.elb.amazonaws.com/

## Scripts

```bash
# Create infra stack
aws cloudformation create-stack --region=us-east-1 --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name project2-infra --template-body file://infra.yml --parameters file://infra-parameters.json

# Create servers stack
aws cloudformation create-stack --region=us-east-1 --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name project2-servers --template-body file://servers.yml --parameters file://servers-parameters.json

# Update infra stack
aws cloudformation update-stack --region=us-east-1 --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name project2-infra --template-body file://infra.yml --parameters file://infra-parameters.json

# Update servers stack
aws cloudformation update-stack --region=us-east-1 --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name project2-servers --template-body file://servers.yml --parameters file://servers-parameters.json
```
