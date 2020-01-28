ARG SHARE_TAG
FROM alfresco/alfresco-share:${SHARE_TAG}

ARG TOMCAT_DIR=/usr/local/tomcat

# Fix for https://github.com/Alfresco/acs-community-packaging/issues/367 in Share 6.2.0
COPY web-extension/share-config-custom-dev.xml $TOMCAT_DIR/shared/classes/alfresco/web-extension/
