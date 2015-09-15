Use the NPM plugin to publish a library to a NPM registry.

The following parameters are used to configuration the publishing:

* **username** - the username for the account to publish with.
* **password** - the password for the account to publish with.
* **email** - the email address associated with the account to publish with.
* **registry** - the registry URL to use (https://registry.npmjs.org by default)
* **folder** - the folder, relative to the workspace, containing the library
  (uses the workspace directory, by default)
* **always_auth** - forces npm to require authentication when accessing the
  registry (false by default)

The following is a sample NPM configuration in your .drone.yml file which
can publish to the global npm registry:

```yaml
publish:
  npm:
    username: $$NPM_USERNAME
    password: $$NPM_PASSWORD
    email: $$NPM_EMAIL
```

For a private npm registry, such as
[Sinopia](https://github.com/rlidwka/sinopia) the following config can be used:

```yaml
publish:
  npm:
    username: $$NPM_USERNAME
    password: $$NPM_PASSWORD
    email: $$NPM_EMAIL
    registry: "http://myregistry:4873"
    always_auth: true
```
