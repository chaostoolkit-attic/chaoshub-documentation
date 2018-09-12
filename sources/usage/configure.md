# Configure the Chaos Hub

## General Settings

The Chaos Hub has a limited number of settings, none of which are mandatory for
a quick trial run.

Configuration is passed through environment variables, either as part of the
process environment, or via a [.env file][dotenv].

[dotenv]: https://github.com/theskumar/python-dotenv

Below is a list of variables that can be set:

| Name                                   | Default                   | Comment                                  |
| -------------------------------------- |:-------------------------:| ----------------------------------------:|
| SERVER_LISTEN_ADDR                     | "0.0.0.0"                 | Adress server will be listening on       |
| SERVER_LISTEN_PORT                     | 8080                      | Port bound                               |
| OAUTH_REDIRECT_BASE                    | "http://127.0.0.1:8080"   | URL OUAth providers redirect to. Should match the domain which you use to access the Chaos Hub |       
| CHERRYPY_PROXY_BASE                    | ""                        | Set it to the http(s)://<DOMAIN> when behind a reverse proxy |
| DB_HOST                                | "sqlite://"               | Database provider host address |
| DB_PORT                                |                           | Database provider port |
| DB_NAME                                | "chaoshub"                | Database name |
| DB_USER                                | ""                        | Database user |
| DB_PWD                                 | ""                        | Database password |
| SECRET_KEY                             | ""                        | Opaque string to sign session cookies. When this changes, all sessions are cleared  |
| CLAIM_SIGNER_KEY                       | ""                        | Opaque string to sign the JWT that is passed between the internal services |
| USER_PROFILE_SECRET_KEY                | ""                        | Opaque string to encrypt user's profile in the database. Using it goes towards GDPR. Losing that value means you won't be able to access any of the user's data. This cannot be recovered |
| GITHUB_CLIENT_ID                       | ""                        | GitHub OAuth application client id |
| GITHUB_CLIENT_SECRET                   | ""                        | GitHub OAuth application secret key |
| GITLAB_CLIENT_ID                       | ""                        | GitLab OAuth application client id |
| GITLAB_CLIENT_SECRET                   | ""                        | GitLab OAuth application secret key |
| GOOGLE_CLIENT_ID                       | ""                        | Google OAuth application client id |
| GOOGLE_CLIENT_SECRET                   | ""                        | Google OAuth application secret key |
| BITBUCKET_CLIENT_ID                    | ""                        | BitBucket OAuth application client id |
| BITBUCKET_CLIENT_SECRET                | ""                        | BitBucket OAuth application secret key |
