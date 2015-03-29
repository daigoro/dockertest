From ubuntu


# Set noninteractive mode for apt-get
ENV DEBIAN_FRONTEND noninteractive

# Upgrade base system packages
RUN apt-get update

### Start editing ###
# Install package here for cache
RUN apt-get -y install software-properties-common \
    && add-apt-repository ppa:freeradius/stable-3.0 \
    && apt-get update \
    && apt-get -y install freeradius freeradius-mysql
	
EXPOSE 1812

# Add files
ADD install.sh /opt/install.sh
RUN ["chmod", "+x", "/opt/install.sh"]

# Run
CMD /opt/install.sh;/usr/sbin/freeradius -f