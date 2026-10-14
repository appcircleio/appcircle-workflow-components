# Appcircle Workflow Component Repository
This repository serves as the master source for the available components for the Appcircle Build module workflows. 
You can find all the officially supported Appcircle workflow components here and contribute to the Appcircle community by sharing your own component.

Appcircle build workflows provide a powerful and flexible way to manage your mobile CI/CD process. You can extend your mobile CI/CD with the rich component library.

## Using the Components
You can find more information about the workflows and how to use a specific component/step in your build in the [Appcircle Documentation](https://docs.appcircle.io/workflows/).

## Contribution
You can create a new component by following the format in the currently available samples, which consist of a YAML file accompanied by a source repository.

## Air-gap support (`airgapSupport`)
Every `<component>/<version>/component.yaml` declares whether the workflow step can run in an air-gapped self-hosted installation, as a top-level line:

```yaml
platform: Common
airgapSupport: true
```

- `true`: the step runs in an air-gapped installation. It may run offline, use only internal services, go through the customer's artifact proxy, or take an input that points it to an internal service.
- `false`: the step needs public SaaS or internet by design, or it needs a code change before it can run air-gapped.

The field is required. The `Validate airgapSupport` GitHub Actions check fails on a pull request when a `component.yaml` has no `airgapSupport: true|false` line, has more than one, or is not at `<component>/<version>/component.yaml`. It blocks the merge once it is set as a required status check. When you add a new component version, set the field in the same pull request. Background: BE-9509.

## Reporting an Issue / Reaching Us
If you encounter any issues related with a component in this repository, you can raise an issue here.

If you have any other issues or questions about Appcircle, you can contact us via our [contact form on Appcircle.io](https://appcircle.io/support) or join our Slack community at [slack.appcircle.io](slack.appcircle.io)
