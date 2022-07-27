# Ansible SSL Scanner

Scan multiple domains SSL certificates and print out informations:

* Host
* Subject
* Issuer
* ExpirationDate

## Usage

Ansible core version 2.13.2 or newer required.

Export domains in to the json file, example from AWS.

```
aws route53 list-resource-record-sets --hosted-zone-id <HostedZoneID> --query "ResourceRecordSets[?Type == 'A'].Name" > domains.txt
```

Then run ansible-playbook command

```
ansible-playbook sslscanner/sslscanner.yml --extra-vars '{"json_file":"./domains_example.txt"}'
```