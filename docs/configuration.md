# Configuration

## Instant messaging apps

See [notes](apps.md#notes) and configure your messaging app

## Alertmanager

See [Alertmanager](alertmanager.md)

## IMPulse

You should set environment variables and configure `impulse.yml`:

### Environment variables

Environment variables is installed in `.env` file for python installation or in `docker-compose.yml` for docker installation. 

To run IMPulse you should set `SLACK_BOT_USER_OAUTH_TOKEN`, `SLACK_VERIFICATION_TOKEN` for Slack installation and `MATTERMOST_ACCESS_TOKEN` for Mattermost.

#### 

| Variable | Description | Default | Required |
|-|-|-|-|
| DATA_PATH | path to data directory | ./data | - |
| CONFIG_PATH | path to `impulse.yml` directory | ./ | - |
| LOG_LEVEL | Log level | INFO | - |
| MATTERMOST_ACCESS_TOKEN | [Mattermost 'Access Token'](apps.md#mattermost) | ./ | for Mattermost |
| SLACK_BOT_USER_OAUTH_TOKEN | [Slack 'Bot User OAuth Token'](apps.md#slack) | | for Slack |
| SLACK_VERIFICATION_TOKEN | [Slack 'Verification Token'](apps.md#slack) | | for Slack |

### impulse.yml

`impulse.slack.yml` (or `impulse.mattermost.yml` for Mattermost) has all available configuration options. By default enabled (without `#`) minimal configuration IMPulse can start with. For additional settings commented out.

On the root level configuration has these blocks:

- timeouts
- route
- application
- webhooks

#### timeouts

`timeouts` block have 3 options: `firing`, `unknown`, `resolved`. For information see comments in [impulse.slack.yml](https://github.com/DiTsi/impulse/blob/main/impulse.slack.yml) or [Concepts](concepts.md).

#### route

Route for Incidents routing based on alert's fields. It made very similar to Alertmanager's [route](https://prometheus.io/docs/alerting/latest/configuration/#route).

#### webhooks

Webhooks used to send POST HTTP requests

See [Webhooks](webhooks.md) to 
undertand how to work with it.