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
aws EC2 describe-security-groups --group-ids sg-029e9b21073e3be13
```
_The Result View_
![image](https://user-images.githubusercontent.com/111234771/200139671-443b3ab1-8284-4442-9e5a-e4cd229dddd0.png)

### ...for Create EC2 Instance - Part 3 ###
```
ec2 run-instances --image-id ami-09d3b3274b6c5d4aa --count 1 --instance-type t2.micro --key-name yir_ec2_key_pair --security-group-ids <Provide the Security Group from the screen created using sg group> --subnet-id subnet-3e88b144
```
