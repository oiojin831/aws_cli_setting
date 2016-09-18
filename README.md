# aws_cli_setting

1. create IAM Group named Admins
2. give AdministratorAccess
3. create IAM User named ++my_name++
4. add user to group
5. Add password for user (click user Actions -> manage password)
6. Change customm IAM users sign-in link:

# After Installed aws-cli
Region: ap-northeast-1

# create ssh keypair
in ~ directory
```bash
mkdir ~/.ssh
aws ec2 create-key-pari --key-name aws-oiojin831 --query 'KeyMaterial' --output text > ~/.ssh/aws-oiojin831.pem
chmod 400 ~/.ssh/aws-oiojin831.pem
```
### verify
```bash
aws ec2 describe-key-pairs --key-name aws-oiojin831
```
### delete
```bash
aws ec2 delete-key-pair --key-name aws-oiojin831
```

# AWS credentials
```bash
aws configure --profile user_name
```
without --profile it sets to default

### aws config credential files
~/.aws/credentials - key and secret
~/.aws/config - region
[default]
[user_name]
중복되게 default로 해야할걸 따로 설정해준다.
default가 아닌경우는 
```bash
aws ec2 describe-instances --profile user2
```
으로 사용해야한다.

 --region us-east-1
