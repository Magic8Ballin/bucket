These are instructions to setup the cs2mod server for the gloveworks server community.

Google Cloud Instance

Project > gloveworks (or My First Project)

Launch Instance
us-central
c2-standard-4
100GB disk
Standard Persistence
No backups/snapshots
No logging
No monitoring

Settings > Metadata
Change IP to the External IP

Configure Firewall
gcloud compute firewall-rules create source \
--allow tcp:27015-27020,tcp:80,udp:27015-27020

Install cs2mod
sudo su
cd / && curl --silent --output "gcp.sh" "https://raw.githubusercontent.com/kus/cs2-modded-server/master/gcp.sh" && chmod +x gcp.sh && bash gcp.sh

Install gloveworks config files
cd /home/steam/cs2/custom && curl --silent --output "gcp.sh" "https://raw.githubusercontent.com/kus/cs2-modded-server/master/gcp.sh" && chmod +x gcp.sh

admins.json
addmin_groups.json
cfg/on_boot.cfg (with gloveworks community server hostname)