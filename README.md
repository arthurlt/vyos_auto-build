# VyOS Auto Build

There's an [IFTTT](https://ifttt.com/) Applet that watches [VyOS GitHub RSS](https://github.com/vyos/vyos-build/tags.atom) for new new tags. This will send a webhook to GitHub and will trigger the workflow. 

The workflow will publish the built ISO to `https://hosted.tuckerfami.ly/public/builds/vyos-{tag}-amd64.iso`.

It's required to have two repository secrets:
| Variable    | Value                  |
| ----------- | ---------------------- |
| WEBDAV_USER | fastmail_email_address |
| WEBDAV_PASS | fastmail_app_password  |

The webook requires a body with an `event_type: ifttt` and `client_payload: {version: {tag}}`
