# artillery-plugin-aws-sigv4-http
A plugin for artillery.io that signs HTTP requests using the AWS Signature V4 specification.

To use:

1. `npm install -g artillery`
2. `npm install -g artillery-plugin-aws-sigv4-http`
3. Add `aws-sigv4-http` plugin config to your "`hello.json`" Artillery script

    ```json
    {
      "config": {
        "plugins": {
          "aws-sigv4-http": {
             "serviceName": "execute-api"
           }
        }
      },
      "scenarios": [
        {
          "beforeRequest": "addAmazonSignatureV4"
        }
      ]
    }
    ```

4. `artillery run hello.json`

This will add an authentication header to every request that conforms to V4 of the AWS Signature Specification.

For more information, see:

* https://github.com/shoreditch-ops/artillery
* http://docs.aws.amazon.com/general/latest/gr/sigv4_signing.html

Enjoy!
