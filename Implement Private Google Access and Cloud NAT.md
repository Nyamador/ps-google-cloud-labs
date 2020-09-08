#### Course Title : Implement Private Google Access and Cloud NAT
#### Course Link:
https://googlepluralsight.qwiklabs.com/focuses/10169034?parent=lti_session

Create a VPC network and firewall rules

Create VPC network

1.

2. Create Firewall rule
```bash
gcloud compute --project=qwiklabs-gcp-00-1478ce6e1914 firewall-rules create privatenet-allow-ssh 
--direction=INGRESS --priority=1000 --network=privatenet --action=ALLOW --rules=tcp:22 --source-ranges=35.235.240.0/20
```

3. Create  A Virtual Machine without a public IP
```bash
gcloud beta compute --project=qwiklabs-gcp-00-1478ce6e1914 instances create vm-internal --zone=us-central1-c --machine-type=n1-standard-1 --subnet=privatenet-us --no-address --maintenance-policy=MIGRATE --service-account=15074866023-compute@developer.gserviceaccount.com --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append --image=debian-9-stretch-v20200902 --image-project=debian-cloud --boot-disk-size=10GB --boot-disk-type=pd-standard --boot-disk-device-name=vm-internal --reservation-affinity=any
```

4. Create a Cloud Storage bucket

5. Copy an image into bucket
```bash
gsutil cp gs://cloud-training/gcpnet/private/access.svg gs://[my_bucket]
```
