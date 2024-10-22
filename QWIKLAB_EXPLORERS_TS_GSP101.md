# Deploy and Troubleshoot a Website: Challenge Lab || [GSP101](https://www.cloudskillsboost.google/focuses/1734?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

```
export INSTANCE=
```
```
export ZONE=
```
```
gcloud compute instances create $INSTANCE --project=$DEVSHELL_PROJECT_ID --zone=$ZONE --machine-type=f1-micro --network-interface=network-tier=PREMIUM,stack-type=IPV4_ONLY,subnet=default --metadata=startup-script=sudo\ su\ -$'\n'$'\n'apt-get\ update$'\n'apt-get\ install\ apache2\ -y$'\n'$'\n'service\ --status-all$'\n',enable-oslogin=true --maintenance-policy=MIGRATE --provisioning-model=STANDARD --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append --tags=http-server,https-server --create-disk=auto-delete=yes,boot=yes,device-name=$INSTANCE,image=projects/debian-cloud/global/images/debian-12-bookworm-v20240312,mode=rw,size=10,type=projects/$DEVSHELL_PROJECT_ID/zones/$ZONE/diskTypes/pd-balanced --no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --labels=goog-ec-src=vm_add-gcloud --reservation-affinity=any

IP=$(gcloud compute instances list $INSTANCE --zones=$ZONE --format='value(EXTERNAL_IP)')

gcloud compute firewall-rules create allow-http \
    --action=ALLOW \
    --direction=INGRESS \
    --target-tags=http-server \
    --source-ranges=0.0.0.0/0 \
    --rules=tcp:80 \
    --description="Allow incoming HTTP traffic"

sleep 20

curl http://$IP
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
