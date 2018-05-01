# wiki.js testing

Below are my personal notes for getting wiki.js up and running. The docker-compose file is made up of 2 containers:

    * MongoDB
    * [wiki.js](https://wiki.js.org/)

### Authentication
By default I have the following authentication methods active:

    * Local
    * Google
    * Github

You can read about OAuth configuration for each method [here](https://docs.requarks.io/wiki/install/authentication). The default acount details are below:

    * User:     {{serverEmail}} (defined in wiki-js.yml)
    * Password: admin123

### Github Integration
In addition to the git options in wiki-js.yml, the following needs to be added under **auth**:

    * signature:
        - name:
        - email:

These options configure git **user.name** and **user.email** respectively. 

Create github.pem with mode 600. This will contain the SSH private key (w/o a passphrase) used to access the Github repo.

### Logging Options

    * bugsnag
    * loggly
    * papertrail
    * rollbar
    * sentry

---
### Further Considerations
