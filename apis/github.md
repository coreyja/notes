# Github API


## Auth

`User-Agent` headers are required: https://docs.github.com/en/rest/overview/resources-in-the-rest-api#user-agent-required

Preferred auth is with the `Authorization: token $GITHUB_TOKEN` header
Source: https://docs.github.com/en/rest/overview/resources-in-the-rest-api#oauth2-token-sent-in-a-header=

This works with oauth tokens and personal access tokens

## Pull Request Diffs

To get the full diff of a PR you need to use a special accept header `application/vnd.github.v3.diff` with the PR API URL.
Ex: `https://api.github.com/repos/coreyja/notes/pulls/1`

Hitting this URL without an accept header will return the standard JSON api response
