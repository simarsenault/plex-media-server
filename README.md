# plex-media-server

## Setup
Create directories:

```
mkdir /home/user/docker
mkdir /home/user/data

mkdir -p /home/user/data/torrents/tv
mkdir -p /home/user/data/torrents/movies
mkdir -p /home/user/data/media/tv
mkdir -p /home/user/data/media/movies
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
Plex: http://ip:32400
Transmission: http://ip:9091/transmission/web
Prowlarr: http://ip:9696
Sonarr: http://ip:8989
Radarr: http://ip:7878