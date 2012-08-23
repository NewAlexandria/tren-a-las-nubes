tren-a-las-nubes
================

AWS package for deploying Locomotive with CloudFormation

This script is simple launch-point for those looking to setup a Mongo-served rails app on Amazon's AWS infrastructure.  It is particularly designed to work with [Locomotive](http://doc.locomotivecms.com/) - a rails CMS.  By using Amazon's CloudFormation templates, you can skillfully manage your usage, track growth, and automate scale.

You will need to search for "blank_" and replace the related tokens with your info (ssh keys, web domains, etc.)

# Dependencies

- Rails 3.2 (you could use ~> 3.0)
- [nginx](http://nginx.org/download/aws_nginx_setup.sh)
- chef
- [LocomotiveCMS](http://www.locomotivecms.com)
- [pygmentize](http://pygments.org/docs/cmdline/)
- [vim.ana](https://github.com/newalexandria/vim.ana)

# Provisions

The following AWS resources will be provisioned when you run this CloudFormation template:

## Resources
### Instances

- MongoInstance:  *EC2 t1.micro*
- WebServer:  *EC2 t1.micro*

### Security

- MongoSecurityGroup: *mongo instance SSH*
- MongodIngress: *mongo data*
- StatusIngress: *mondo updates*
- FrontendSecurityGroup: *web instance SSH*

### EBS

- MongoVolume1

## Not Provisioned

The following are currently excluded because they contain data specific to anyones' individual setup.  

- IAM Profile
- 53Routes (DNS)


# What's Coming

- Template blanks for AWS users and routes
- Chef recipes for configuring things past the bootstrap (nginx, locomotive
- Deploy dependencies to standardized places
- CLI inputs for vim and less augmentation 
