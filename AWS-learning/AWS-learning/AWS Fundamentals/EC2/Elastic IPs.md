# Elastic IPs

When you stop and then start an EC2 instance, it can change its public IP

If you need to have a fixed public IP for your instance you need an Elastic IP

An Elastic IP is a public IPv4 you own as long as you don't delete it you can attach it to one instance at a time

With an Elastic IP address you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account

you can only have 5 Elastic IP in your account (you  can ask AWS to increase that)

Overall, try to avoid using Elastic IP (often reflect poor architectural decisions)

instead use a random public IP and register a DNS name to it or use a load balancer and don't use a public IP (best pattern for AWS)