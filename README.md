Fail2Ban Action Configuration for CloudFlare REST API V4 using Authorization Bearer Token
========================================================

Note: _This will only work if you have full access to your web server's `/etc/fail2ban/` files._

Installation:

* Copy [action.d/cloudflare-restv4-bearer-token.conf](https://github.com/wpkc/fail2ban-action-cloudflare-restv4-bearer-token/blob/master/action.d/cloudflare-restv4-bearer-token.conf) to your `/etc/fail2ban/action.d` directory.
* Get your CloudFlare Authoriation Bearer Token API Key at: <https://dash.cloudflare.com/profile/api-tokens>.  Your Authorization Bearer Token must have read-write-delete access to your firewall rules.
* Modify your `/etc/fail2ban/jail.local` as shown in the sample [jail.local](https://github.com/wpkc/fail2ban-action-cloudflare-restv4-bearer-token/blob/master/jail.local) file provided in this repository. Set `cftoken` to your cloudflare Authoriztion Bearer Token.
* Restart Fail2Ban with: `service fail2ban restart`
* Please consider using [mod_cloudflare](https://github.com/cloudflare/mod_cloudflare) on Apache2 servers to make sure you are using the correct IP address as the client IP address.

**Be sure to review the issue about [permissions assigned to your CloudFlare token](https://github.com/wpkc/fail2ban-action-cloudflare-restv4-bearer-token/issues/1).  If not, you may get authentication errors.**

More info: <https://www.kazimer.com/fail2ban-cloudflare-action-using-authorization-bearer-token/>
