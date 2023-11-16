# action-infisical

A GH action that retrieves secrets from Infisical using an API instead of installing a client binary and outputs them to a file.

**NOTE 1**: This action depends on `jq` and `curl` being installed in the environment where it is run.

**NOTE 2**: In order to use this GitHub Action, you need to **disable E2EE** in Infisical for the workspace in question. This has some security implications - do this at your own risk.

## Inputs

### `infisical_token`

**Required** Infisical API Token.

## `workspace_id`

**Required** Infisical Workspace ID.

### `environment`

**Required** The environment to fetch secrets for (e.g., staging, production).

### `output_file`

**Optional** Output file path. Defaults to `.env`.

### `secret_path`

**Optional** Secret path. Defaults to `/`.

### `api_url`

**Optional** Infisical API URL. Defaults to `https://api.infisical.com`.

## Example usage

```yaml
uses: zerodays/action-infisical@v1
with:
  infisical_token: ${{ secrets.INFISICAL_TOKEN }}
  environment: "staging"
```
