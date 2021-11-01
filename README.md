# EDC 2021 conference, Radix application example
Example demonstrates deploy-only Radix option, building the application on external Continuous Integration (CI) tool and deploy it from private image container registry (CR).

* Application use [build-in python HTTP server](https://docs.python.org/3/library/http.server.html)
* CI - [GitHub Actions](https://github.com/features/actions)
* CR - [GitHub pachages](https://github.com/features/packages)
* Radix CLI creates a deploy-only job, via [Radix GiHub Action](https://github.com/equinor/radix-github-actions). 
* GitHub repository has a secret `K8S_CREDENTIALS` - Radix machine-user token, generated in Radix Console for this application (Configuration page). It is used to set environment variable `APP_SERVICE_ACCOUNT_TOKEN` to access Radix API by Radix CLI.
* Two environments of the application are deployed from different image tags: `main-latest` and `release-latest`.
* For private container registries - add property `privateImageHubs` to the `radixconfig.yaml` and put personal access token to `Radix Console/Configuration/App Secrets/Private image hubs`  
```yaml
 privateImageHubs:
    container-repository-URL:
      username: user-name
      email: user-email
```
More information is available in the [Radix documentation](https://www.radix.equinor.com/), also particularly about [deploy-only](https://www.radix.equinor.com/guides/deploy-only).