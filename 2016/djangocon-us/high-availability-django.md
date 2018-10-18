# High-Availability Django
## Frankie Dintino, The Atlantic

### Ideas

* OpBeat
* model instantiation and hydration
* The Atlantic only uses 3 webservers behind Nginx
* uWSGI over mod_wsgi
* keeps machines running, stages new code, warms up python modules, switches symlinks to deploy, uses uWSGI zerg mode

### Profiling

* New Relic, OpBeat
* django-debug-toolbar, django-silk
* cProfile
* WSGI middleware

### Monitoring

* Alertra, New Relic, OpBeat, Chartbeat
* Nagios

### Caching

* Use a CDN with proper headers (consider crawlers and bots)
* Proxy cache (Nginx, Squid, Varnish) Nginx set short cache time but long store time that will keep a cached "up" version of the site until the new version has a 200 response
* Django Cache Framework
* Page caching frameworks
* ORM caching: django-cache-machine (mixed bag)

### Query Optimization

* prefetch_related, select_related
* prefetch_related_objects for generic foreign keys
* values and values_list
* Database parameter tuning, heavy indexing
