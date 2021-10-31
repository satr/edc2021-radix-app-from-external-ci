# EDC 2021 conference, Radix application example
Example demonstrates deploy-only Radix option, building the application on external Continuous Integration (CI) tool and deploy it from private image container registry (CR).

* Application use [build-in python HTTP server](https://docs.python.org/3/library/http.server.html)
* CI - [GitHub Actions](https://github.com/features/actions)
* CR - [GitHub pachages](https://github.com/features/packages)
* GitHub repository has a secret `K8S_CREDENTIALS` - Radix machine-user token, generated in Radix Console for this application (Configuration page).
* Two environments of the application are deployed from different image tags: `main-latest` and `release-latest`.

More information is available in the [Radix documentation](https://www.radix.equinor.com/), also particularly about [deploy-only](https://www.radix.equinor.com/guides/deploy-only).