# Move Issues

Move Issues is a GitHub App built with [Probot](https://github.com/probot/probot)
that moves issues between repositories.

<p>
  <img width="420" src="https://raw.githubusercontent.com/dessant/move-issues/master/assets/source-issue.png">
  <img width="420" src="https://raw.githubusercontent.com/dessant/move-issues/master/assets/target-issue.png">
</p>

## Supporting the Project

Move Issues is an MIT-licensed open source project. Its ongoing
development is made possible thanks to the support of awesome backers.
If you'd like to join them, please consider contributing with
[Patreon](https://goo.gl/qRhKSW), [PayPal](https://goo.gl/5FnBaw)
or [Bitcoin](https://goo.gl/uJUAaU).

## Usage

1. **[Install the GitHub App](https://github.com/apps/move)**
   for all source and target repositories
2. Create `.github/move.yml` in the source repository based on the template below
3. Move an issue by creating a comment with this command: `/move to <repo>`

Users must have certain permissions in order to move issues:

* Write access to the source repository
* Write access to the target repository when the source and target repositories
  have different owners, or when the target repository is private

#### Configuration

Create `.github/move.yml` in the default branch of the source repository
to enable the app. The file can be empty, or it can override any of these
default settings:

```yaml
# Configuration for move-issues - https://github.com/dessant/move-issues

# Delete the command comment when it contains no other content
deleteCommand: true

# Close the source issue after moving
closeSourceIssue: true

# Lock the source issue after moving
lockSourceIssue: false

# Mention issue and comment authors
mentionAuthors: true

# Preserve mentions in the issue content
keepContentMentions: false

# Set custom aliases for targets
# aliases:
#   r: repo
#   or: owner/repo
```

#### Command Syntax

```
/move [to ][<owner>/]<repo>
```

###### Examples:

```
/move to repo
/move to owner/repo
/move repo
/move owner/repo
```

## Deployment

See [docs/deploy.md](docs/deploy.md) if you would like to run your own
instance of this app.

## License

Move Issues is released under the terms of the MIT License.
Please refer to the [LICENSE](LICENSE) file.
