# hubot.system
CentOS 7 Hubot systemd (with Mattermost adapter)

## Setup
* Install and setup Hubot (https://hubot.github.com/docs/) with Mattermost adapter (https://github.com/renanvicente/hubot-mattermost)
* Place hubot.system into /etc/systemd/system/
 
If you have more than one Hubot running on your server you can use multiple system files with different names (there may be a better way of doing this).

### Modify hubot.system:
* Set up your Mattermost enviromental variables.
* Set the system user to run hubot as. I have my hubot running as 'hubot'
* Set your WorkingDirectory and ExecStart to point to your hubot directory

### Setup Systemd
* `systemctl daemon-reload`
* `systemctl enable hubot`
* `systemctl start hubot`

### Troublshooting
* `systemctl status hubot`
* `less /var/log/messages`

I had a few issues with NPM permissions and global packages. I kept receiving:
- `Error: Cannot find module 'hubot-mattermost'`

To fix my issue I used 'Option 2' on this site: https://docs.npmjs.com/getting-started/fixing-npm-permissions and reinstalled my npm packages as hubot. 

