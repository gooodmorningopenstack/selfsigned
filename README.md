Generate a self signed x509 certificate from node.js.

[![Build Status](https://travis-ci.org/jfromaniello/selfsigned.png)](https://travis-ci.org/jfromaniello/selfsigned)

## Install

```bash
  npm install selfsigned
```

## Basic usage

```js
const selfsigned = require('selfsigned');
selfsigned.generate()
  .catch(err => console.log(err))
  .then(cert => console.log(cert));
```
Will return an object with the following keys and values :

```js
{
  private: '-----BEGIN RSA PRIVATE KEY-----\r\nMIICXAIBAAKBgQCBFMXMYS/+RZz6+qzv+xeqXPdjw4YKZC4y3dPhSwgEwkecrCTX\r\nsR6boue+1MjIqPqWggXZnotIGldfEN0kn0Jbh2vMTrTx6YwqQ8tceBPoyuuqcYBO\r\nOONAcKOB3MLnZbyOgVtbyT3j68JE5V/lx6LhpIKAgY0m5WIuaKrW6mvLXQIDAQAB\r\nAoGAU6ODGxAqSecPdayyG/ml9vSwNAuAMgGB0eHcpZG5i2PbhRAh+0TAIXaoFQXJ\r\naAPeA2ISqlTJyRmQXYAO2uj61FzeyDzYCf0z3+yZEVz3cO7jB5Pl6iBvzbxWuuuA\r\ncbJtWLhWtW5/jioc8F0EAzZ+lkC/XuVJdwKHDmwt2qvJO+ECQQD+dvo1g3Sz9xGw\r\n21n+fDG5i4128+Qh+JPgh5AeLuXSofc1HMHaOXcC6Wu/Cloh7QAD934b7W0A7VoD\r\ndLd/JLyFAkEAgdwjryyvdhy69e516IrPB3b+m4rggtntBlZREMrk9tOzeIucVO3W\r\ntKI3FHm6JebN2gVcG+rZ+FaDPo+ifJkW+QJBAPojrMwEACmUevB2f9246gxx0UsY\r\nbq6yM3No71OsWEEY8/Bi53CEQqg7Gq5+F6H33qcHmBEN8LQTngN9rY+vZh0CQBg0\r\nqJImii5B/LeK03+dICoMDDmCEYdSh9P+ku3GZBd+Lp3xqBpMmxDgi9PNPN2DwCs7\r\nhIfPpwGbXqtyqp7/CkECQB4OdY+2FbCciI473eQkTu310RMf8jElU63iwnx4R/XN\r\n/mgqN589OfF4SS0U/MoRzYk9jF9IAJN1Mi/571T+nw4=\r\n-----END RSA PRIVATE KEY-----\r\n',
  public: '-----BEGIN PUBLIC KEY-----\r\nMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCBFMXMYS/+RZz6+qzv+xeqXPdj\r\nw4YKZC4y3dPhSwgEwkecrCTXsR6boue+1MjIqPqWggXZnotIGldfEN0kn0Jbh2vM\r\nTrTx6YwqQ8tceBPoyuuqcYBOOONAcKOB3MLnZbyOgVtbyT3j68JE5V/lx6LhpIKA\r\ngY0m5WIuaKrW6mvLXQIDAQAB\r\n-----END PUBLIC KEY-----\r\n',
  cert: '-----BEGIN CERTIFICATE-----\r\nMIICjTCCAfagAwIBAgIBATANBgkqhkiG9w0BAQUFADBpMRQwEgYDVQQDEwtleGFt\r\ncGxlLm9yZzELMAkGA1UEBhMCVVMxETAPBgNVBAgTCFZpcmdpbmlhMRMwEQYDVQQH\r\nEwpCbGFja3NidXJnMQ0wCwYDVQQKEwRUZXN0MQ0wCwYDVQQLEwRUZXN0MB4XDTEz\r\nMDgxMzA1NDAyN1oXDTE0MDgxMzA1NDAyN1owaTEUMBIGA1UEAxMLZXhhbXBsZS5v\r\ncmcxCzAJBgNVBAYTAlVTMREwDwYDVQQIEwhWaXJnaW5pYTETMBEGA1UEBxMKQmxh\r\nY2tzYnVyZzENMAsGA1UEChMEVGVzdDENMAsGA1UECxMEVGVzdDCBnzANBgkqhkiG\r\n9w0BAQEFAAOBjQAwgYkCgYEAgRTFzGEv/kWc+vqs7/sXqlz3Y8OGCmQuMt3T4UsI\r\nBMJHnKwk17Eem6LnvtTIyKj6loIF2Z6LSBpXXxDdJJ9CW4drzE608emMKkPLXHgT\r\n6MrrqnGATjjjQHCjgdzC52W8joFbW8k94+vCROVf5cei4aSCgIGNJuViLmiq1upr\r\ny10CAwEAAaNFMEMwDAYDVR0TBAUwAwEB/zALBgNVHQ8EBAMCAvQwJgYDVR0RBB8w\r\nHYYbaHR0cDovL2V4YW1wbGUub3JnL3dlYmlkI21lMA0GCSqGSIb3DQEBBQUAA4GB\r\nAC9hGQlDh8anNo1YDJdG2mYqOQ5uybJV++kixblGaOkoDROPsWepUpL6kMDUtbAM\r\n4uXTyFkvlUQSaQkhNgOY5w/BRIAkCIu6u4D4XcjlCdwFq6vcKMEuWTHMAlBWFla3\r\nXJZAPO10PHuDen7JeMOUf1Re7lRFtwfRGAvVYmrvYFKv\r\n-----END CERTIFICATE-----\r\n'
}
```
## Advanced usage

```js
selfsigned.generate(certAttributes, options)
  .catch(err => console.log(err))
  .then(cert => console.log(cert));
```

## Certificate attributes and options

```js
const certAttributes = [
  {
    name: 'commonName',
    value: 'helloworld.paris',
  },
  {
    name: 'countryName',
    value: 'France',
  },
  {
    shortName: 'ST',
    value: 'FR',
  },
  {
    name: 'localityName',
    value: 'Paris',
  },
  {
    name: 'organizationName',
    value: 'Hello World Corporation',
  },
  {
    shortName: 'OU',
    value: 'Hello World Corporation',
  }
];

const options = {
  keySize: 2048, // the size for the private key in bits (default: 2048)
  validForDays: 30, // signed certificate expiration time (default: 365)
  certExtensions: [
    {
      name: 'basicConstraints',
      cA: true,
    },
    {
      name: 'subjectAltName',
      altNames: [{
        type: 6,
        value: 'http://example.org/webid#me',
      }
  ],
  exportAsPkcs7: true, // include PKCS#7 as part of the output (default: false)
}
```

You can avoid key pair generation specifying your own keys in the options object.
```js
const options = {
  keyPair: {
    publicKey: '-----BEGIN PUBLIC KEY-----...',
    privateKey: '-----BEGIN RSA PRIVATE KEY-----...'
  }
  /* ... */
};
```

## License

MIT
