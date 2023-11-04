permisos:
	@ chmod 600 ./traefik-data/acme.json
utils:
	@ sudo apt install apache2-utils
password:
	@ echo $$(htpasswd -nb traefik-admin top_secret)
network:
	@ docker network create --driver overlay --attachable --scope swarm traefik-public  || true
rm:
	@ docker stack rm traefik
deploy:
	@ docker stack deploy -c stack.yml traefik
portainer:
	@ docker stack deploy -c stack.yml portainer
label:
	@ docker node update --label-add onlyproxy=true proxy
rm-portainer:
	@ docker stack rm portainer
