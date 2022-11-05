# AWS CLI

### ...for Installation of AWS CLI - Part-1 ###
_Go to Command Prompt and paste the below and also follow on screen instation_
_for window_
```
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
```
_Close the Terminal and restart to verify the version of AWS_
```
aws --version
```
_...for Auto complication_

### ...for Create Security with Ingress permission - Part-2 ###
```
 aws ec2 create-security-group --group-name my-sg --description "my sg grp" --vpc-id vpc-07b1ad3dcb8a7e3a9
```
_The Result View_
![image](https://user-images.githubusercontent.com/111234771/200139351-f590b305-8511-4755-ba37-67e7894b7355.png)

```
aws ec2 authorize-security-group-ingress --group-id sg-029e9b21073e3be13 --protocol tcp --port 0-65535 --cidr 0.0.0.0/0
```
_Note: Protocal Can Be_
![image](https://user-images.githubusercontent.com/111234771/200139494-2ea2f493-7b80-49ae-ad42-c8aa79ada662.png)

_The Result View_
![image](https://user-images.githubusercontent.com/111234771/200139506-415292db-0775-47fa-9a9f-c90aa5119705.png)

_Get More Details about the Security Group_
```
aws ec2 describe-security-groups --group-ids sg-029e9b21073e3be13
```
_The Result View_
![image](https://user-images.githubusercontent.com/111234771/200139671-443b3ab1-8284-4442-9e5a-e4cd229dddd0.png)

***...For Deleting Security Group***
```
aws ec2 delete-security-group --group-id sg-029e9b21073e3be13
```
### ...for Create Key Pair - Part 3 ###
```
aws ec2 create-key-pair --key-name yirkeypair --query 'KeyPairMaterial' --output text > yirkeypair.pem
chmod 400 yirkeypair.pem
aws ec2 describe-key-pairs --key-names yirkeypair
```
_The Result View_
![image](https://user-images.githubusercontent.com/111234771/200140657-a6820751-5985-4b60-82b2-6c9335b31b06.png)

***...For Deleting***
```
aws ec2 delete-key-pair --key-name yirkeypair
```

### ...for Create EC2 Instance - Part 4 ###
***Note:*** Follow KeyPair Creation (Part 3) and Security Group (Part2)
![image](https://user-images.githubusercontent.com/111234771/200141291-efdf8468-01b8-412d-b9ef-2267c1099b37.png)
```
aws ec2 run-instances --image-id ami-09d3b3274b6c5d4aa --count 1 --instance-type t2.micro --key-name yirkeypair --security-group-ids sg-0432b7a4a3b80bb87 --subnet-id subnet-0f2a848f31da8feb8
```
_The Result View_ ***Note: subnet id need to collect***
![image](https://user-images.githubusercontent.com/111234771/200141388-c1697df6-1ab6-4129-ba05-0863288be388.png)
