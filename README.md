# eao-nginx
Nginx configuration for the Ministry of Energy and Mines.

## Example rollout usage

### nginx proxy deployment for mem-mmt-dev environment:
```
oc process -f https://raw.githubusercontent.com/bcgov/esm-server/master/openshift/templates/rproxy-build-template.json -v BUILDER_IMAGESTREAM_TAG=s2i-nginx:latest -v SOURCE_REPO
SITORY_URL=https://github.com/bcgov/mem-nginx -v NGINX_PROXY_URL=http://mem-mmt-dev:3000 -v NAME=rproxy | oc create -f -
```
### nginx proxy deployment for mem-mmt-dev environment:

```
oc process -f https://raw.githubusercontent.com/bcgov/mem-nginx/master/openshift/templates/rproxy-environment-template.json -v APPLICATION_DOMAIN=mem-mmt-dev.pathfinder.gov.bc.c
a -v APP_DEPLOYMENT_TAG=latest -v APP_IMAGE_NAMESPACE=mem-mmt-tools APP_IMAGE_NAME=rproxy -v NAME=rproxy-master NGINX_PROXY_HOST=mem-mmt-dev.pathfinder.gov.bc.ca | oc create -f -
```

