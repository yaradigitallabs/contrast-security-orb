# contrast-security-orb

Yara Digital Farming Contrast Security Orb for CircleCI

The Contrast agent begins securing your code by adding sensors to the entire software stack of your applications - from runtime to custom code - to directly measure vulnerabilities and attacks. Contrast Assess continuously monitors all your code, including your libraries, for known and unknown vulnerabilities, and produces accurate results without dependence on application security experts.

## Documentation

This orb is a fork of https://github.com/Contrast-Security-OSS/contrast-security-orb v0.3.0 with changed calling conventions, like in this example:

```
  contrast-verify:
    executor: contrastsecurity/default
    steps:
      - checkout
      - contrast_verify/check-vulnerabilities:
          contrast-url: 'https://app.contrastsecurity.com/Contrast'
          username: CONTRAST_USERNAME
          service-key: CONTRAST_SERVICE_KEY
          org-id: CONTRAST_ORG_ID
          severities: CONTRAST_SEVERITIES
          api-key: CONTRAST_API_KEY
          vulnerability-threshold: CONTRAST_VULNERABILITY_THRESHOLD
          application-id: CONTRAST_APPLICATION_ID
```

All parameters except for `contrast-url` are sourced through environment variables. The values in the example are the defaults, and can be omitted:

```
- contrast_verify/check-vulnerabilities
```

should be a valid way to call the orb, provided that the correct environment is set on the `contrast-verify` job.
