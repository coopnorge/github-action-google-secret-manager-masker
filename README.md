# Google Secrets Manager


```yaml
name: 'Google Secrets Masker '
description: |
  This action will load all secrets from Google Secrets Manager. This make sure that
  the values always will be masked in the logs if they somehow accidently leak. It requires
  the github to google auth.
inputs:
  workload_identity_provider:
    description: |
      The path of the workload identity provider. See config of "google-github-actions/auth@v0.8.0"
    required: true
  service_account:
    description: |
      The service account which can read the secrets. It required the role "roles/secretmanager.viewer" on the project
      and the "roles/secretmanager.Accessor" on the secrets you want to mask. See config of "google-github-actions/auth@v0.8.0"
    required: true
  filter:
    description: |
      Filter the secrets to be masked. See https://cloud.google.com/secret-manager/docs/filtering. Defaults to ""
    required: false
    default: ""
```