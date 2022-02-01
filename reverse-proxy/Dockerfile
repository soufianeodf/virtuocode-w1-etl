FROM nginx:1.21.6-alpine

RUN apk --update --no-cache upgrade \
    && apk add git vim \
	&& rm -rf /var/lib/apt/lists/*

COPY nginx.conf /etc/nginx/nginx.conf
