<!-- note marker start -->
**NOTE**: This repo contains only the documentation for the private BoltsOps Pro repo code.
Original file: https://github.com/boltopspro/toolset/blob/master/README.md
The docs are publish so they are available for interested customers.
For access to the source code, you must be a paying BoltOps Pro subscriber.
If are interested, you can contact us at contact@boltops.com or https://www.boltops.com

<!-- note marker end -->

# toolset configset

![CodeBuild](https://codebuild.us-west-2.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiRGlkd0JLNE1WYmNLays1TklvdXVSNXhEOTJvdGltTG94SEowSVIzTldWZzNFL1AxWS8xQVB2Smt5SW1uZ29SZk9oK0U1SS9BeXJyTkZOUFBpVWEzblJBPSIsIml2UGFyYW1ldGVyU3BlYyI6InBKQ250ekU0cmxFZ2lJZlAiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master)

[![BoltOps Badge](https://img.boltops.com/boltops/badges/boltops-badge.png)](https://www.boltops.com)

This configset will install common linux utils like tree, jq, etc.

## What are lono configsets?

Lono configsets allow CloudFormation [cfn-init](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-init.html) [configsets](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-init.html) that are typically embedded in the template to be reusable.  More info: [Lono Configsets docs](https://lono.cloud/docs/configsets/).

## Usage

Use `configset` to enable the configset for the blueprint.  Example:

configs/demo/configsets/base.rb:

```ruby
configset("toolset", resource: "Instance")
```

This adds the configset to the `resource` with the logical id `Instance` in your CloudFormation template.  The configset is added to the [Resources[].Metadata.AWS::CloudFormation::Init](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-init.html) attribute of the `Instance` resource.

Here's an example adding to a `LaunchConfig` resource:

```ruby
configset("toolset", resource: "LaunchConfig")
```

Here's an example adding to a `LaunchTemplate` resource:

```ruby
configset("toolset", resource: "LaunchTemplate")
```
