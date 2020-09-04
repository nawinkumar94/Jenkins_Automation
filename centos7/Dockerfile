FROM centos:7

#installing openssh-server
RUN yum -y install openssh-server

#installing passwd
RUN yum -y install passwd

# creating user and directory for user and setting password and permissions
RUN useradd remote_user && \
    echo "1234" | passwd remote_user --stdin && \
    mkdir /home/remote_user/.ssh && \
    chmod 700 /home/remote_user/.ssh

# copy the public key to created path
COPY remote-key.pub /home/remote_user/.ssh/authorized_keys

#Making the created use as owner to access keys and change permission
RUN chown remote_user:remote_user	    -R /home/remote_user && \
    chmod 600 /home/remote_user/.ssh/authorized_keys

#RUN /usr/sbin/ssh-keygen

#generating key for docker
RUN yum install -y initscripts \
    && /usr/sbin/sshd-keygen

# To install mysql
RUN yum -y install mysql

# To install pip and awscli
RUN yum -y install epel-release && \
    yum -y install python-pip && \
    pip install --upgrade pip && \
    pip install awscli

CMD ["/usr/sbin/sshd", "-D"]
