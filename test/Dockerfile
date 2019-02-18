FROM debian:stretch

ENV DEBIAN_FRONTEND noninteractive

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
ADD . /app

RUN apt-get update \
&& apt-get -y install apt-utils \
&& apt-get -y upgrade \
&& apt-get -y install python-pip python-dev \
&& apt-get -y install curl wget gnupg \
&& apt-get -y install nmap htop

RUN curl -sL https://deb.nodesource.com/setup_9.x | /bin/bash \
&& apt-get -y install nodejs \
&& npm install -g archeyjs

RUN pip install -U pip setuptools wheel future \
&& pip install -U jupyter numpy matplotlib


# Install any needed packages
#RUN apt-get update && apt-get -y upgrade \
#&& apt-get -y install apt-utils \
#&& apt-get update && apt-get -y upgrade \
#&& apt-get -y install python python-dev python-pip python-setuptools python-pkg-resources \
#build-essential git cmake swig pkg-config \
#nmap htop arp-scan wget curl \
#&& useradd -ms /bin/bash -G sudo pi


# jp2a figlet libfreetype6 libfreetype6-dev libpng libpng12-dev \
# && pip install -U pip setuptools wheel \
# && pip install -U future \
# && pip install -U --trusted-host pypi.python.org -r requirements.txt \

# Make port 80 available to the world outside this container
EXPOSE 8080

#USER pi
#WORKDIR /home/pi

CMD archeyjs
CMD /bin/bash
