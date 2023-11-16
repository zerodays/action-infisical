# action-infisical

A GitHub action that retrieves secrets from Infisical using an API instead of installing a client binary and outputs them to a file. This allows it to be really fast.

This action **is unofficial** and was created by the [zerodays](https://github.com/zerodays) team for our own internal use. Feel free to use it, but note that it is not officially supported by Infisical.

**NOTE 1**: In order to use this GitHub Action, you need to **disable E2EE** in Infisical for the workspace in question. This has some security implications - do this at your own risk.

**NOTE 2**: This action depends on `jq` and `curl` being installed in the environment where it is run.

## Inputs

### `infisical_token`

**Required** Infisical API Token.

### `workspace_id`

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
  workspace_id: ${{ secrets.INFISICAL_WORKSPACE_ID }}
  environment: "staging"
```
