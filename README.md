# prs-merged-since

This is a simple tool to list the PRs merged in a GitHub repo since a certain tag.

You can use it to find all the PRs merged since your last release, for example.

## CLI Usage

```
Options:
  --help     Show help                                                 [boolean]
  --version  Show version number                                       [boolean]
  --repo     GitHub repository, eg Microsoft/vscode                   [required]
  --tag      Tag to show merged PRs relative to, eg 1.1.3             [required]
  --format   Output format. Can be 'json' or 'markdown'.       [default: "json"]
  --references  Extract link references when format is markdown
                                                      [boolean] [default: false]
```

For example:

```sh
$ prs-merged-since --repo prettier/prettier --tag 1.11.1
```

You can provide a GitHub API Authorization Token by using the `GITHUB_API_TOKEN` environment variable:

```
$ GITHUB_API_TOKEN=your_token_goes_here prs-merged-since --repo prettier/prettier --tag 1.11.1
```

## JS Usage

There is also a JavaScript API:

```js
const prsMergedSince = require("prs-merged-since");

prsMergedSince({
  repo: "prettier/prettier", // required
  tag: "1.11.1", // required
  githubApiToken: "your_token_goes_here", // optional
}).then((prs) => {
  // prs is an array of PR objects as returned by the GitHub API
});
```

## License

MIT
