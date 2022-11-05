# AWS CLI

###...for Installation of AWS CLI - Part-1###
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

###...for Create Security with Ingress permission - Part-2###
```
ec2 authorize-security-group-ingress --group-id sg-0ad8f48de242b1e3 --protocol tcp --port 0-65535 --cidr 0.0.0.0/0
```
```
ec2 authorize-security-group --group-id sg-0ad8f48de242b1e3
```
###...for Create EC2 Instance###
```
ec2 run-instances --image-id <Provider your AMI > --count 1 --instance-type t2.micro --key-name <Provide your Key Name> --security-group-ids <Provide the Security Group from the screen created using sg group> --subnet-id subnet-3e88b144
```
