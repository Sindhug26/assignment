# python1
FROM openshift/base-centos7
#FROM Pythoncalc

 LABEL maintainer="sindhugsg01@gmail.com"


# ENV BUILDER_VERSION 2.0

# TODO: Set labels used in OpenShift to describe the builder image
LABEL io.k8s.description="Platform for building Python application \
      io.k8s.display-name="builder python_calc" \
     io.openshift.expose-services="8080:http" \
      io.openshift.tags="builder,calc,etc."

# TODO: Install required packages here:
# RUN yum install -y ... && yum clean all -y
RUN yum install -y rubygems && yum clean all -y
RUN gem install asdf
RUN yum install python

# TODO (optional): Copy the builder files into /opt/app-root
# COPY ./C:\Users\sindhu\Documents\Docker\test\test-app\python/ /opt/app-root/

# TODO: Copy the S2I scripts to /usr/libexec/s2i, since openshift/base-centos7 image
# sets io.openshift.s2i.scripts-url label that way, or update that label
COPY ./C:\Users\sindhu\Documents\Docker\test\test-app\python/ /usr/libexec/s2i

# TODO: Drop the root user and make the content of /opt/app-root owned by user 1001
# RUN chown -R 1001:1001 /opt/app-root

# This default user is created in the openshift/base-centos7 image
USER 1001

# TODO: Set the default port for applications built using this image
 EXPOSE 8080

# TODO: Set the default CMD for the image
CMD ["python",./Calculator.py]
