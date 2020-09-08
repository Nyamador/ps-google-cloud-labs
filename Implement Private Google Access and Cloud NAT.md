Course Title : Implement Private Google Access and Cloud NAT
Link: https://googlepluralsight.qwiklabs.com/focuses/10169034?parent=lti_session

Create a VPC network and firewall rules

Create VPC network
1.

2. Create Firewall rule
```bash
gcloud compute --project=qwiklabs-gcp-00-1478ce6e1914 firewall-rules create privatenet-allow-ssh 
--direction=INGRESS --priority=1000 --network=privatenet --action=ALLOW --rules=tcp:22 --source-ranges=35.235.240.0/20
```
