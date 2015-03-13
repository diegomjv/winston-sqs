# Amazon SQS Transport for [winston][0] [![Build Status](https://api.travis-ci.org/agad/winston-sqs.png)](http://travis-ci.org/agad/winston-sqs)
## Installation via npm

``` sh
  $ npm install winston
  $ npm install winston-sqs
```
## Usage
``` js
  var winston = require('winston');
  require('winston-sqs').SQS;
  winston.add(winston.transports.SQS, options);
```

The Winston SQS transport depends on [aws-sdk](https://github.com/aws/aws-sdk-js).

The constructor options are:

* __aws_credentials:__ [`AWS.Credentials`][1] instance, f.ex. `AWS.EC2MetadataCredentials` 
  or `AWS.EnvironmentCredentials` *[required this or key+secret]*
* __aws_accesskeyid:__ Your Amazon Public Key. *[required this or aws_credentials]*
* __aws_secretaccesskey:__ Your Amazon Secret. *[required this or aws_credentials]*
* __aws_queueurl:__ The specific queue URL to write to.  Found in your AWS Console. *[required]*
* __aws_region:__ AWS Region to use. (default: `us-east-1`)
* __level:__ default logging level. (default: `info`)
* __aws_sslenabled:__ whether to use SSL in communication with SQS. (default: true)
* __aws_maxretries:__ number of times to retry communication with SQS. (default: 3)
* __debug:__ log error/response after each message sent (default: false)
* __formatter:__ custom log formatting function, as in the core Winston transports (default: undefined)
* __timestamp:__ whether to include a timestamp in the queue message. (default: true)

Note that metadata will be automatically 'stringified.'

[0]: https://github.com/flatiron/winston
[1]: http://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/Credentials.html
