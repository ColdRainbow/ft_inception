
all:
	docker build . -t nginx
	docker run --name nginx -d nginx
clean:
	docker system prune -a
re: clean all

