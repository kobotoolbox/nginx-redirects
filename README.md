# kobo-support-docker

This repository handles redirection and reverse proxying for some domains:

* support.kobotoolbox.org:
    1. If the request path matches a specific path that was previously used, it redirects it to the new page
    1. Otherwise, the request is reverse-proxied to https://kobotoolbox.github.io, which is our documentation website.
* help.kobotoolbox.org:
    1. Requests to the base hostname are now redirected to the Discourse forum,  https://community.kobotoolbox.org;
    1. Requests for anything else are redirected to https://support.kobotoolbox.org.
* forum.kobotoolbox.org: this was the very short-lived original hostname for our Discourse forum. This redirect could probably be removed, but for now, it steers people to https://community.kobotoolbox.org.
* koboresearch.com: redirected to koboresearch.org
* koboresearch.org: redirected to kobotoolbox.org
* kobotoolbox.com: redirected to kobotoolbox.org
* eu.kobotoolbox.org: redirected to https://kobo.humanitarianresponse.info
* kobotoolbox.org: requests to https://kobotoolbox.org/anything are redirected to https://www.kobotoolbox.org/anything;
* kobo.ngo: requests to the base hostname and `www` sub-domain are redirected to https://www.kobotoolbox.org;
* kobo.ong: requests to the base hostname and `www` sub-domain are redirected to https://www.kobotoolbox.org;
* eu.kobotoolbox.org: requests to the base hostname are redirected to https://kobo.humanitarianresponse.info;

## How to use
Apply changes to the us-east-1 EKS cluster: `./bin/apply`
