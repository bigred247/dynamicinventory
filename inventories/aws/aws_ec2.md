plugin: aws_ec2
regions:
  - eu-west-1
  - eu-west-2
  - eu-west-3
strict_permissions: False
hostnames:
  - tag:Name
keyed_groups:
  - key: tags['Application']
  - key: tags['Environment']
  - key: tags['Role']
  - key: tags['AMI']
  - key: tags['OperatingSystem']
  - key: placement.region
    parent_group: regions
    prefix: ''
    separator: ''
compose:
  ansible_host: private_ip_address
