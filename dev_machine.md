http://docs.aws.amazon.com/cli/latest/userguide/tutorial-ec2-ubuntu.html

aws ec2 run-instances --image-id ami-a21529cc --security-group-ids sg-17e0fd73 --count 1 --instance-type t2.micro
keyname도 줘야하는데 ec2 dashboard에서 만들면됨. 그럼 public이 저장된상태에서 만들어지는거 같다
chmod 400 dev-machine.pem

availability-zone은 필수
aws ec2 create-volume --availability-zone ap-northeast-1a --size 30

aws ec2 attach-volume --devise/dev/sda1 --volume-id instance-id

이렇게 각자하는 방법을 찾다 보니까 cloudformation 이라는게 있다! 굳

문서 찾아가면서 cli에 쓰는거 optional 아닌것만 잘 넣어주면됨, key string안에 대소문자 조심하면됨
디버깅하는게 겁나 짜증난다. cli로 해보고 채워넣는 형식으로
[x] volume이 하나더 생기 
[x] 30짜리를 gp2로 해야될거같음
따로 설정하는게 아니라 ec2에 있었음

http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html

dev-machine file참조

```bash
aws cloudformation create-stack --stack-name dev-machine --template-url https://s3-ap-northeast-1.amazonaws.com/cf-templates-1oz3rylt2bho3-ap-northeast-1/2016269RmW-dev-machine3j8jnubvt4a3eoctyov5i2j4i
```
```bash
sh -c "$(wget https://raw.githubusercontent.com/oiojin831/laptop/master/init.sh -O -)"
```
### Install plugin in vim  
PlugInstall
