
Configure your [AWS access 
keys](http://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) as 
environment variables:

1.
Once you have a `.aws` directory installed on your local machine, you will need to edit the `aws_credentials_file` in `main.tf` in order to provide the path to `.aws`.
it should look something like `/Users/username/.aws`

2.
once you have built a custom docker image of social-network and published to your dockerhub repo you will need to change the code in main.tf where it launches the chevdor image to whichever your desired image is.

```
export AWS_ACCESS_KEY_ID=(your access key id)
export AWS_SECRET_ACCESS_KEY=(your secret access key)
```

Deploy the code:

```
terraform init
terraform apply
```

When the `apply` command completes, it will output the DNS name of the load balancer. 

Clean up when you're done:

```
terraform destroy
```