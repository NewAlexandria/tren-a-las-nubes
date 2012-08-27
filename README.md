tren-a-las-nubes
================
*[(Train to the clouds)](http://en.wikipedia.org/wiki/Tren_a_las_Nubes)*


AWS package for deploying [Locomotive](http://www.locomotivecms.com) with [CloudFormation](http://aws.amazon.com/cloudformation/)

This script is simple launch-point for those looking to setup a Mongo-served rails CMS on Amazon's AWS infrastructure.  By using Amazon's CloudFormation templates, you can skillfully comprehend your resources, manage usage, track growth, and automate scale.

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

The following are currently excluded because;

1. the data they contain specific to an individual setup.  
2. reaffirming #1, you cannot make a template for new HostedZones (DNS base NS records).

If that's confusing to you, consider the major use-case for automating the creation of DNS entries: spammers and search-engine manipulators whom create profuse domain records..

- IAM Profile
- 53Routes (DNS)


# What's Coming

- Template blanks for AWS users and routes
- Chef recipes for configuring things past the bootstrap (nginx, locomotive
- Deploy dependencies to standardized places
- CLI inputs for vim and less augmentation 
