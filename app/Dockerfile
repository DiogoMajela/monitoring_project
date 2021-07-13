FROM centos
RUN yum install wget gcc openssl-devel cairo cairo-devel libxslt-devel libffi-devel gcc-c++ kernel-devel gobject-introspection-devel cairo-gobject cairo-gobject-devel epel-release -y 
RUN yum install python2-pip -y
COPY Requirements.txt /srv/
RUN cd /srv/ && pip2.7 install -r Requirements.txt
RUN yum remove gcc kernel-devel gcc-c++ -y
RUN yum clean all
RUN rm -rf /var/cache/yum
COPY app.py /srv/
CMD ["python2.7", "/srv/app.py"]
