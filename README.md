# plex-media-server

## Install
Replace `user` by your username and `1000:1000` by your user id and group id. 

Create directories:

```
mkdir /home/user/docker
mkdir /home/user/data

mkdir -p /home/user/docker/transmission-home

mkdir -p /home/user/data/completed/radarr
mkdir -p /home/user/data/completed/sonarr
mkdir -p /home/user/data/media/tv
mkdir -p /home/user/data/media/movies

mkdir -p /home/user/docker/seerr/config
sudo chown -R "1000:1000" "/home/user/docker/seerr/config"
```

Copy the .env file:

```
cp .env.example .env
```

Start:

```
docker compose up -d
```

Validate transmission VPN:

```
docker compose exec transmission curl -s https://ipinfo.io | grep -E '"(ip|country)"'
```

## URLS
- Plex: http://ip:32400
- Transmission: http://ip:9091/transmission/web
- Prowlarr: http://ip:9696
- Sonarr: http://ip:8989
- Radarr: http://ip:7878
- Seerr: http://ip:5055