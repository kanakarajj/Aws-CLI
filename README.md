# Aws-CLI
Deregister ELB


Deregister_instances from elb_

[root@ip-x-xx-xx-xx old_script]# cat deregister_inst_elb_old.sh

Command $ - ./deregister_inst_elb.sh  i-00c15440671c3a2f3

echo "deregistering $1 from load balancers"

prod_elb=prodloadbalancer1
edsoft_elb=edsoft-prd-elb

aws elb deregister-instances-from-load-balancer --load-balancer-name $prod_elb --instances $1 --region us-east-1
echo " deregistered $prod_elb "
aws elb deregister-instances-from-load-balancer --load-balancer-name $edsoft_elb --instances $1 --region us-east-1
