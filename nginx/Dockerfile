FROM centos:8

RUN \
#  add-apt-repository -y ppa:nginx/stable && \
  dnf update -y && \
  dnf -y install nginx && \
  dnf clean all
RUN rm -rf /var/lib/apt/lists/* 

COPY nginx.conf /etc/nginx/nginx.conf
COPY app.conf /etc/nginx/conf.d/app.conf

EXPOSE 80 

#CMD ["nginx"]
CMD ["nginx", "-g", "daemon off;"]
