# Terraform / AWS / SNS
Terraform module for SNS Topic on AWS.

## Terraform versions

Terraform 0.12.x

## Usage

```hcl
locals {
  tags_mandatory = {
    owner  = "AFPOpsTeam"
    prefix = "snstest"
  }
}

module "sns" {
  source = "app.terraform.io/afp-hub/sns/aws"
  
  name  = "my-topic"
  tags_mandatory = local.tags_mandatory
}
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:----------:|
| name | Topic's name | string | `""` | yes |
| tags_mandatory | Mandatory tags | object | {} | yes |
| tags_custom | Custom tags | object | {} | no |
| display_name | The display name for the SNS topic | string | null | no
| policy | The fully-formed AWS policy as JSON | string | null | no
| delivery_policy | The SNS delivery policy | string | null | false
| application_success_feedback_role_arn | The IAM role permitted to receive success feedback for this topic | string | null | no
| application_success_feedback_sample_rate | Percentage of success to sample | string | null | no
| application_failure_feedback_role_arn | IAM role for failure feedback | string | null | no
| http_success_feedback_role_arn | The IAM role permitted to receive success feedback for this topic | string | null | no
| http_success_feedback_sample_rate | Percentage of success to sample | string | null | no
| http_failure_feedback_role_arn | IAM role for failure feedback | string | null | no
| lambda_success_feedback_role_arn | The IAM role permitted to receive success feedback for this topic | string | null | no
| lambda_success_feedback_sample_rate | Percentage of success to sample | string | null | no
| lambda_failure_feedback_role_arn | IAM role for failure feedback | string | null | no
| sqs_success_feedback_role_arn | The IAM role permitted to receive success feedback for this topic | string | null | no
| sqs_success_feedback_sample_rate | Percentage of success to sample | string | null | no
| sqs_failure_feedback_role_arn | IAM role for failure feedback | string | null | no
| kms_master_key_id | The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK | string | null | no


## Outputs

| Name | Description | Type |
|------|-------------|:----:|
| sns_topic_arn | ARN of SNS topic | string |

## Authors

Module is maintained by [AFPOpsTeam](https://bitbucket.org/afpopsteam/terraform-aws-sns/src/master/)
