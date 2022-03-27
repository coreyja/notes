# Github API

## Auth

`User-Agent` headers are required
> Source [https://docs.github.com/en/rest/overview/resources-in-the-rest-api#user-agent-required](https://docs.github.com/en/rest/overview/resources-in-the-rest-api#user-agent-required)

Preferred auth is with the `Authorization: token $GITHUB_TOKEN` header.
This works with oauth tokens and personal access tokens
> Source: [https://docs.github.com/en/rest/overview/resources-in-the-rest-api#oauth2-token-sent-in-a-header=](https://docs.github.com/en/rest/overview/resources-in-the-rest-api#oauth2-token-sent-in-a-header=)

## Pull Request Diffs

To get the full diff of a PR you need to use a special accept header `application/vnd.github.v3.diff` with the PR API URL.
Ex: `https://api.github.com/repos/coreyja/notes/pulls/1`

Hitting this URL without an accept header will return the standard JSON api response
