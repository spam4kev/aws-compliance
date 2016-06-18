# aws-compliance

To enforce standards on your AWS instances, put this script in an init cron of your AMI. Upon creation of a new instance off the AMI, the cron runs and the script looks at AWS's meta data url (http://169.254.169.254/1.0/meta-data/) to check if the instance doesn't have any values determined to be naught. If a bad value is found, the instance is powered off leaving those with power to create instances in AWS wondering why their machine keeps shutting off.

This all happens within the first minute of the instances creation so as to not give users enough time grow a dependency on the instance.
