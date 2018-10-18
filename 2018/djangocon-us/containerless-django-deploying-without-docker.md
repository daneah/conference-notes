# "Containerless Django: Deploying without Docker" by Peter Baumgartner


## Arguments for Docker

* The "pipeline"
* Security via sandboxing
* Isolation of dependencies, etc.
* Dev/test/prod parity


## Arguments against Docker

* Lightweight, but slower than some other solutions
* Extra abstractions
* A lot of software; O(millions of lines of Go code)


## History

### Deployments sucked

* Dependency management not perfect; libraries can change underneath you
* Build tools and packages need to be installed
* Multiple languages, frameworks, and builds for full stack applications


#### The ideal deployment

1. Download a binary
1. Configure the binary
1. Run the binary


### Python

* Requires a virtual machine to run
* Uses dynamic linking to other libraries that aren't part of the application dependencies explicitly
* Packaging isn't straightforward


## Now

* `pipenv` and `poetry` are improving dependency management and consistency
* Pre-compiled wheels are becoming more available, reducing pieces you need to build yourself
* virtualenvs, static files, and a production webserver are still gaps


## Existing solutions

* Private PyPI
* `virtualenv-clone`
* Platter
* `dh-virtualenv`
* Pex


## ZIP applications

* Present since 2.6, improved in 3.5 via PEP-441
* Create a ZIP archive of your project and run it with Python
* No dependency management, but `shiv` might help
`.pyz` extension


## Production webserver

* `gunicorn` + `whitenoise`
* `django-pyuwsgi`


## What this looks like

`$ ./yourproject.pyz pyuwsgi --http=:8000`

Only requires Python to be installed!


## Configuration

* Same ZIP application artifact, different settings per environment
* Options:
  * Multiple settings files and the `DJANGO_SETTINGS_MODULE` variable
  * Environment variables
  * `goodconf`


## The ZIP app pipeline

* Use a CI tool to:
  1. Build the ZIP app artifact
  1. Test the artifact (with `./yourproject.pyz test`, for example)
  1. Push the artifact somewhere accessible to prod servers
* Deploy:
  1. Download artifact
  1. Configure (unless automated)
  1. Run application


## Security

* `systemd` has your back!
  ```systemd
  ProtectSystem=strict  # Makes filesystem read-Only
  ProtectHome=true  # Removes access to home directories
  DynamicUser=true  # Create an anonymous user for running this application
  CapabilityBoundingSet=~CAP_SYS_ADMIN  # Disallow all permissions the cap sys admin group has
  AppArmorProfile=srv.yourproject.pyz
  ...
  ```


## Isolation

You still need Python globally, but it's easy to install multiple versions with e.g. `pyenv`.


## Parity

The ZIP application is the same artifact from CI all the way to production deploy.
