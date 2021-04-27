# EC2 User Data
It is possible to “bootstrap” our instance using an EC2 User data script

`bootstraping`: means launching commands when a machine starts

the script is only run once at the instance first start

EC2 user data is used to automate boot tasks such as

*   installing updates
*   installing software
*   downloading common files from the internet

The EC2 User Data Script runs with the root user (sudo rig