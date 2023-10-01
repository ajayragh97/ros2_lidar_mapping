BASE_CONT_NAME=humble

up:
	docker compose up -d

enter:
	xhost +local:docker
	clear && docker exec -it ${BASE_CONT_NAME} bash -c "source ~/.bashrc && bash"

down:
	docker compose down
