network:
	@ docker network create --driver overlay --attachable --scope swarm service_net || true
	@ docker network create --driver overlay --attachable --scope swarm traefik-public  || true

install-portainer:
	@ docker volume create portainer_data
	@ docker network create --driver overlay --attachable --scope swarm agent_network  || true
deploy:
	@ docker stack deploy --with-registry-auth 	-c stack.yml portainer
rm:
	@ docker stack rm portainer
