# ForgeRock DevOps and Cloud Deployment

_Kubernetes deployment for the ForgeRock&reg; Identity Platform._

This repository provides Docker and Kustomize artifacts for deploying the 
ForgeRock Identity Platform on a Kubernetes cluster. 

This GitHub repository is a read-only mirror of
ForgeRock's [Bitbucket Server repository](https://stash.forgerock.org/projects/CLOUD/repos/forgeops). 
Users with ForgeRock BackStage accounts can make pull requests on our Bitbucket 
Server repository. ForgeRock accepts pull requests on GitHub for review only.

## Disclaimer

>This repository is provided on an “as is” basis, without warranty of any kind, 
to the fullest extent permitted by law. ForgeRock does not warrant or guarantee 
the individual success developers may have in implementing the code on their
development platforms or in production configurations. ForgeRock does not 
warrant, guarantee or make any representations regarding the use, results of use,
accuracy, timeliness or completeness of any data or information relating to these 
samples. ForgeRock disclaims all warranties, expressed or implied, and in 
particular, disclaims all warranties of merchantability, and warranties related
to the code, or any service or software related thereto. ForgeRock shall not be
liable for any direct, indirect or consequential damages or costs of any type 
arising out of any action taken by you or others related to the samples.

## How to Work With This Repository

See [About the forgeops repository](https://ea.forgerock.com/docs/forgeops/start/repositories.html) in the ForgeOps documentation for information about how to work with this pre-release software.

>Note: The forgeops repository’s master branch contains pre-release software that is not supported by ForgeRock.

If you want to work with the latest stable forgeops repository release, use the 
[latest release branch](https://github.com/ForgeRock/forgeops/tree/release/7.5-20240402) and the [latest release documentation](https://backstage.forgerock.com/docs/forgeops/7.5/index.html).

## What's New?

See the [ForgeOps Release Notes](https://backstage.forgerock.com/docs/forgeops/7.5/rn/rn.html) to read about new features and changes.

## ForgeRock Identity Platform Configuration

The provided configuration, which we call the Cloud Developer's Kit (CDK),
is a basic installation that can be further extended by developers to meet their requirements. 
The main features of the CDK configuration are:

* Deployments for ForgeRock AM, IDM, DS and IG. IG is not deployed by default, but is available optionally.
* AM configured with a single root realm.
* A number of OIDC clients configured for AM/IDM integration and for smoke tests.
Note that the `idm-provisioning`, `idm-admin-ui` and the `end-user-ui` client configurations are required for the
integration of IDM and AM.
* Directory service instances configured for:
   * The shared AM/IDM repo (ds-idrepo).
   * The AM dynamic runtime data store for policies and agents. Currently, the ds-idrepo is used.
   * The Access Manager Core Token Service (ds-cts).
* A Gatling test harness, which exercises the basic deployment and can be modified to include additional tests.

## Getting Started

If you just want to observe the ForgeRock Identity Platform in action on a 
Kubernetes cluster, you can try out our ForgeOps deployment. You'll need to install 
the required third-party software, set up a Kubernetes cluster, and install the 
ForgeRock Identity Platform. 

See the [Setup](https://ea.forgerock.com/docs/forgeops/setup/overview.html) and [Deployment](https://ea.forgerock.com/docs/forgeops/deploy/overview.html) sections in the documentation for detailed information about all these tasks.

## Accessing Platform UIs and APIs

See [UI and API access](https://ea.forgerock.com/docs/forgeops/deploy/access.html) in the ForgeOps documentation.

## Secrets

ForgeRock uses secrets generated by [Secret Agent Operator](https://github.com/ForgeRock/secret-agent).
 

## Troubleshooting Tips

See [Troubleshooting](https://ea.forgerock.com/docs/forgeops/troubleshoot/overview.html) in the ForgeOps documentation.

## Cleaning up

See [Remove a ForgeOps deployment](https://ea.forgerock.com/docs/forgeops/deploy/remove.html) in the ForgeOps documentation. 

## References

[About the forgeops repositories](https://ea.forgerock.com/docs/forgeops/start/repositories.html)

[Benchmark authentication rate](https://ea.forgerock.com/docs/forgeops/prepare/benchmark/authrate.html)

[ForgeOps Release Notes](https://ea.forgerock.com/docs/forgeops/rn/rn.html)

[The latest release branch](https://github.com/ForgeRock/forgeops/tree/release/7.5-20240402)

[The latest release documentation](https://backstage.forgerock.com/docs/forgeops/7.5/index.html)

[Statement of support](https://backstage.forgerock.com/docs/forgeops/7.5/start/support.html#kubernetes-services)

[Troubleshooting](https://ea.forgerock.com/docs/forgeops/troubleshoot/overview.html)

[UI and API access](https://ea.forgerock.com/docs/forgeops/deploy/access.html)

## License
This project is licensed under the CDDL License - see the [LICENSE](LICENSE) file for details
Copyright 2024 Ping Identity Corporation. All Rights Reserved.
