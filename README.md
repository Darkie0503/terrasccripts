# vpc

`###
aws ec2 create-vpc --cidr-block 10.88.0.0/16
aws ec2 create-subnet --vpc-id $VPC_ID --cidr-block 10.88.0.0/24 --availability-zone us-east-1e
aws ec2 create-subnet --vpc-id $VPC_ID --cidr-block 10.88.1.0/24 --availability-zone us-east-1f
aws ec2 create-subnet --vpc-id $VPC_ID --cidr-block 10.88.2.0/24 --availability-zone us-east-1e
aws ec2 create-subnet --vpc-id $VPC_ID --cidr-block 10.88.3.0/24 --availability-zone us-east-1f
aws ec2 create-internet-gateway
aws ec2 attach-internet-gateway --vpc-id $VPC_ID --internet-gateway-id $IGW
aws ec2 create-route-table --vpc-id $VPC_ID
aws ec2 create-route --route-table-id $RTB --destination-cidr-block 0.0.0.0/0 --gateway-id $IGW
aws ec2 allocate-address --domain vpc
aws ec2 create-nat-gateway --subnet-id $PUBLIC_SUBNET --allocation-id $EIP
aws ec2 create-route-table --vpc-id $VPC_ID
aws ec2 create-route --route-table-id $RTB_PRIVATE --destination-cidr-block 0.0.0.0/0 --gateway-id $NGW
aws ec2 associate-route-table --subnet-id $PUBLIC_SUBNET0 --route-table-id $RTB_PUB
aws ec2 associate-route-table --subnet-id $PUBLIC_SUBNET1 --route-table-id $RTB_PUB
aws ec2 associate-route-table --subnet-id $PRIVATE_SUBNET2 --route-table-id $RTB_PRIV
aws ec2 associate-route-table --subnet-id $PRIVATE_SUBNET3 --route-table-id $RTB_PRIV
`###
