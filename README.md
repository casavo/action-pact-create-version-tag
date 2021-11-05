# pact-create-version-tag-action

# GitHub Action - Pact Create Version Tag

This action uses [pact-cli](https://github.com/pact-foundation/pact-ruby-cli) 
docker image to perform an opinionated "create version tag" task:

```
pact broker create-version-tag --pacticipant <PACTICIPANT> --version <COMMIT_SHA> --tag <ENVIRONMENT>
```
