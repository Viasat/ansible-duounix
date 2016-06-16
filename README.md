# duounix

This is a fairly uncomplicated role for installing Duo Security's
[duo_unix](https://duo.com/docs/duounix) on a system, to protect things like SSH
or console access. We intentionally **don't** handle things like PAM
configuration in this role, because those will vary widely by use case.

# Configuration

**Bold** items are required.

| Variable                      | Default                                                       | Notes                                     |
| --------                      | -------                                                       | -----                                     |
| **duounix_integration_key**   | None                                                          |                                           |
| **duounix_secret_key**        | None                                                          |                                           |
| **duounix_api_hostname**      | None                                                          |                                           |
| duounix_install               | package                                                       | could be `package` or `source`            |
| duounix_conf_dir              | /etc/duo                                                      |                                           |
| duounix_login_config          | `{failmode: secure, pushinfo: yes, autopush: no, prompts: 3}` | any extra config you want for login_duo   |
| duounix_pam_config            | `{failmode: secure, pushinfo: yes, autopush: no, prompts: 3}` | any extra config you want for pam_duo     |

If building from source, the following variables take effect:

| Variable                      | Default                                                       | Notes                                     |
| --------                      | -------                                                       | -----                                     |
| duounix_checksum              | 2eb11dff0a173c62e31...                                        | SHA256 hash of the file                   |
| duounix_path                  | https://dl.duosecurity.com/                                   |                                           |
| duounix_version               | 1.9.18                                                        |                                           |
| duounix_prefix_dir            | /usr                                                          |                                           |
| duounix_build_pam             | yes                                                           |                                           |
