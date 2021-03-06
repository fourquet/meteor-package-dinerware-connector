[![Build Status](https://travis-ci.org/fourquet/meteor-package-dinerware-connector.svg?branch=master)](https://travis-ci.org/fourquet/meteor-package-dinerware-connector)
Connect to a Dinerware POS
=============================
This package allows for connecting to a Dinerware POS Brain. Meteor server must be on the Brain terminal or in the network with the SQL Server on the brain accessible to
network computers with password authentication. Package uses [tedious](https://www.npmjs.com/package/tedious) and [tedious-connection-pool](https://www.npmjs.com/package/tedious-connection-pool) npm packages.
## Install
To install in a new project, fork or download this repository and put in the packages directory in a meteor project.

## Use
Configure Dinerware object by adding [connection details](https://www.npmjs.com/package/tedious-connection-pool) to your setting.json file like:
```json
{
  "dinerware": {
    "connection": {
      "userName": "login",
      "password": "password",
      "server": "localhost"
    },
    "connectionPool": {
      "min": "2",
      "max": "4",
      "log: true
    }
  }
}
```
You can also configure Dinerware by passing config details directly:
```javascript
var poolConfig = {
    min: 2,
    max: 4,
    log: true
};
var connectionConfig = {
    userName: 'login',
    password: 'password',
    server: 'localhost'
};
Dinerware.config(poolConfig, connectionConfig);
```
Currently, this package only prints query results. You can fork and add your own methods. Submit a PR if you like. To print query results:
```javascript
Dinerware.printQuery('SELECT * FROM SomeTable');
```
### Version
1.13.1_1

License
----

MIT
