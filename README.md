# Pact Create Version Tag Action

This action uses [pact-cli](https://github.com/pact-foundation/pact-ruby-cli) 
docker image to perform an opinionated "create version tag" task:

```console
$ pact broker create-version-tag \
    --pacticipant <PACTICIPANT> \
    --version <COMMIT_SHA> \
    --tag <ENVIRONMENT>
```

## Inputs

Action inputs are (hopefully) kept in sync with related option of [`create-version-tag` command](https://github.com/pact-foundation/pact_broker-client#create-version-tag) by `pact-cli`

### `pacticipant`

**Required** The pacticipant name.

### `version`

**Required** The pacticipant version.

### `tag`

**Required** Tag name for pacticipant version. **WARNING**: only one tag name can specified by now.

## Environment Variables

Setup environment variables used by `pact-cli`.

### `PACT_BROKER_BASE_URL`

**Required** The base URL of the Pact Broker

### `PACT_BROKER_USERNAME`

**Required** Pact Broker basic auth username

### `PACT_BROKER_PASSWORD`

**Required** Pact Broker basic auth password

## Example usage
```yml
steps:
  # ...
  - uses: casavo/pact-create-version-tag-action@v1
    env:
      PACT_BROKER_BASE_URL: ${{ secrets.PACT_BROKER_BASE_URL }}
      PACT_BROKER_PASSWORD: ${{ secrets.PACT_BROKER_PASSWORD }}
      PACT_BROKER_USERNAME: ${{ secrets.PACT_BROKER_USERNAME }}
    with:
      pacticipant: my-application
      version: ${GITHUB_SHA}
      tag: staging
  # ...
```
