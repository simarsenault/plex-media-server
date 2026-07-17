# plex-media-server

## Install
Replace `user` by your username and `1000:1000` by your user id and group id. 

### Create directories

```
mkdir /home/user/docker
mkdir /home/user/data

mkdir -p /home/user/docker/tautulli

mkdir -p /home/user/data
mkdir -p /home/user/data/media/tv
mkdir -p /home/user/data/media/movies

mkdir -p /home/user/docker/seerr/config
sudo chown -R "1000:1000" "/home/user/docker/seerr/config"
```

### Copy the .env file

```
cp .env.example .env
```

### Start

```
docker compose up -d
```

### Validate glueton VPN

```
docker compose exec gluetun wget -qO- ifconfig.me ifconfig.me | grep ip_addr:
```

### Enable API acces in qbittorrent

Check for qbittorrent password in logs:

```docker compose logs qbittorrent```

Open http://ip:8080 and use user `admin` and password found in logs.

In `Settings` -> `BitTorrent`:
1. Uncheck `Enable DHT (decentralized network) to find more peers`
2. Uncheck `Enable Peer Exchange (PeX) to find more peers`
3. Save

In `Settings` -> `WebUI`:
1. Set a new password for the user `admin`
2. Check `Bypass authentication for clients on localhost`
3. Save

## URLS
- Plex: http://ip:32400
- qbittorrent: http://ip:8080
- Prowlarr: http://ip:9696
- Sonarr: http://ip:8989
- Radarr: http://ip:7878
- Seerr: http://ip:5055
- Tautulli: http://ip:8181