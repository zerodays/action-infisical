# action-infisical

A GH action that retrieves secrets from Infisical using an API instead of installing a client binary and outputs them to a file.

## Inputs

### `infisical_token`

**Required** Infisical API Token.

### `environment`

**Required** The environment to fetch secrets for (e.g., staging, production).

### `output_file`

**Optional** Output file path. Defaults to `.env`.

### `api_url`

**Optional** Infisical API URL. Defaults to `https://api.infisical.com`.

## Example usage

```yaml
uses: zerodays/action-infisical@master
with:
  infisical_token: ${{ secrets.INFISICAL_TOKEN }}
  environment: "staging"
```
