# blockcast

## Install Dependecies:

## Register Dashboard:
To get started, register in [Dashboard](https://app.blockcast.network?referral-code=QCsKOk)



```bash
docker compose exec blockcastd blockcastd init
```
```bash
cd blockcast
```

## Get Location:
```bash
curl -s https://ipinfo.io | jq '.city, .region, .country, .loc'
```
