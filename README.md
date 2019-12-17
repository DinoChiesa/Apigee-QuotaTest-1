# Quota Demonstration

This directory includes:

- an API proxy that demonstrates
  the Quota behavior and use within Apigee Edge.

- a tool to provision and de-provision the demonstration

## License

This example and all its code and configuration
is Copyright (c) 2019 Google LLC, and is released under the
Apache Source License v2.0. For information see the [LICENSE](LICENSE) file.

## Disclaimer

This example is not an official Google product, nor is it part of an official Google product.


## Example use

Provision:
```
node provisionQuotaDemo.js -v -u myapigeeid@example.com -o $ORG -e $ENV
```


To use the proxy, copy-paste the client id and secret from the output of the above:
```
client_id=gnOJ9mVAsps8Nbcy5gjtu3K2szvkjwMi
client_secret=IQlZWCMBYvKqDeZ0
```

Get a new token :

```
curl -i -X POST -H "content-type: application/x-www-form-urlencoded" \
  -u ${client_id}:${client_secret} \
  -d "grant_type=client_credentials" \
  https://amer-demo46-test.apigee.net/quotatest/oauth2-cc/token
```

Copy-paste the token and then Use the token:
```
access_token=TOKEN_FROM_ABOVE
curl -i -H "Authorization: Bearer ${access_token}" \
  https://amer-demo46-test.apigee.net/quotatest/ops/withtoken

```


De-provision:
```
node provisionQuotaDemo.js -v -u myapigeeid@example.com -o $ORG -e $ENV -R
```


## Author

Dino Chiesa
godino@google.com

