# Specify a base image
FROM amazonlinux:2

# Update all packages
RUN yum -y update

# Install apache inside the container
RUN yum install -y httpd

# Copy the app inside the container -> /var/www/html
COPY index.html /var/www/html/

EXPOSE 80

# systemctl start httpd (service) run apache
ENTRYPOINT ["/usr/sbin/httpd"]

# run in the background
CMD ["-D", "FOREGROUND"]
