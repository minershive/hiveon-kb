title: Teleconsole

## Teleconsole
Teleconsole is an SSH tunnel to your rig. In few words you start it on the rig and open SSH in browser or in Linux/Mac console. This does not require any VPN or being in local network.

The product website: https://www.teleconsole.com/.

To start it run this with Linux Shell Execute on web: `telec start`.
Then copy-paste given link to the browser. Or run `teleconsole join <given id>` on your Linux/Mac terminal.

Run `telec` to see if it’s running, check other commands like `stop`, `log open`.

### Security
Teleconsole IS NOT started automatically. You need to start it from the web. Given session id is almost impossible to guess, it’s almost like to guess a private key for your bitcoin wallet. Treat it like a random login and password.

If you don’t connect for 60 minutes the link will expire and Teleconsole daemon will be terminated on the rig.
