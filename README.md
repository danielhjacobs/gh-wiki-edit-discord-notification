# GitHub Action - Project Wiki Edit Discord Notifications

GitHub Action to notify a Discord channel when someone edits the a project wiki.

## Inputs

* `discord-webhook-url`: (required, string) A discord channel webhook URL 
* `ignore-contributors`: (optional, boolean, default = `false`) Ignore edits made by repo contributors
* `discord-username`: (optional, string, default = `github-actions`) The bot username for Discord
* `discord-avatar-url`: (optional, string) The bot avatar url for Discord

## Discord Webook URL

This should be set as an [Action Secret](https://docs.github.com/en/rest/actions/secrets).

## Example usage

```yml
name: Wiki Changed Discord Notifications

on:
  gollum

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - uses: 'oznu/gh-wiki-edit-discord-notification@main'
        with:
          discord-webhook-url: ${{ secrets.DISCORD_WEBHOOK_WIKI_EDIT }}
          ignore-contributors: true
```