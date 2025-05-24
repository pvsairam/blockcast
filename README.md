# Blockcast Network
A DePIN in content delivery networks to earn with idle internet bandwidth, powered by solana.

### Reward Details:
A 6-month Proof of Resources Epoch, rewarding nodes based on their node capacity.

* Top-performing nodes will receive special NFTs at the end of the epoch.

- **Reward rate is based on:**
  - Connection quality (your uplink speed)
  - Reliability (consistent uptime)
  - Hardware score (RAM, disk, CPU)
  - Location (where your IP is physically based)
  - BONUS: Multicast-enabled IPs earn extra points!
- Possible to run with a minimal hardware.

---

## Install Dependecies:
Update packages:
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
Install Packages:
```bash
sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
Install Docker:
```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world

sudo systemctl enable docker
sudo systemctl restart docker
```

---

## Register Dashboard:
To get started, register in [Dashboard](https://app.blockcast.network?referral-code=XlWh6d)

---

## Install
```bash
git clone https://github.com/0xmoei/blockcast
```
```bash
cd blockcast
```

---

## Run
```bash
docker compose up -d
```

---

## Check Logs
List Containers:
```bash
docker compose ps -a
```
Response:
```
NAME                                 IMAGE                             COMMAND                  SERVICE          
beacon-docker-compose-watchtower-1   containrrr/watchtower             "/watchtower"            watchtower
beacond                              blockcast/cdn_gateway_go:stable   "/usr/bin/beacond -l…"   beacond
blockcastd                           blockcast/cdn_gateway_go:stable   "/usr/bin/blockcastd…"   blockcastd
control_proxy                        blockcast/cdn_gateway_go:stable   "/usr/bin/control_pr…"   control_proxy
```
Check logs:
```bash
docker compose logs -fn 1000
```
* skip logs if you have all containers running.

---

## Register Node
Get location:
```bash
curl -s https://ipinfo.io | jq '.city, .region, .country, .loc'
```

Generate Node Data & Register:
```bash
docker compose exec blockcastd blockcastd init
```
* Copy and paste the `Registration URL` from the terminal in browser to open the Dashboard.
* With your Hardware ID and Challenge Key pre-filled, Fill-in your location from previous command.
* Register your Node.

![image](https://github.com/user-attachments/assets/e81a9eb2-291a-4d9b-a5db-72999f14b473)

* Wait a few minutes until your node truns **Online**

![image](https://github.com/user-attachments/assets/b7fd77ab-2ee0-4086-bb56-c2746ad8ee1e)


