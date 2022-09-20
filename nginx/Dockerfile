FROM nginx:1.21.4

RUN apt-get update && \
	apt-get install zip -y

RUN rm /etc/nginx/conf.d/*
COPY ./nginx.conf /etc/nginx/conf.d/nginx.conf

COPY ./lib_letsencrypt.zip /tmp/
COPY ./etc_letsencrypt.zip /tmp/

RUN unzip ./tmp/etc_letsencrypt.zip -d /tmp/
RUN unzip ./tmp/lib_letsencrypt.zip -d /tmp/

RUN cp /tmp/etc/letsencrypt /etc/ -r
RUN cp /tmp/var/lib/letsencrypt /var/lib/ -r

COPY ./placeholder_html/index.html /www/data/
COPY ./placeholder_html/blog_index.html /www/data/
COPY ./placeholder_html/chat_index.html /www/data/
COPY ./placeholder_html/hire_index.html /www/data/
COPY ./placeholder_html/mail_index.html /www/data/
COPY ./placeholder_html/portfolio_index.html /www/data/
COPY ./placeholder_html/resume_index.html /www/data/
COPY ./placeholder_html/HMIn2YbhjtqKyHa9W77WGnQdDZ0uJwXr802KOtYo9dM.html /www/data/.well-known/acme-challenge/HMIn2YbhjtqKyHa9W77WGnQdDZ0uJwXr802KOtYo9dM/