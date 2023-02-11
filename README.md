## ufwApps

Application Profiles for UFW

### Usage

* Copy the profile you wish to use into `/etc/ufw/applications.d/`
  ```
  arrorn@server:~/ufwApps$ sudo cp ./valheim /etc/ufw/applications.d/.
  ```
* Verify UFW reads the profile by running `sudo ufw app list`
  The profile you copied should be in the listed application profiles.
  ```
  arrorn@server:~/ufwApps$ sudo ufw app list
  Available applications:
    Arma3
    Valheim
    Cockpit
    OpenSSH
    Teamspeak
    Teamspeak ServerQuery Raw
    Teamspeak ServerQuery SSH
    Teamspeak TSDNS
    Teamspeak WebQuery HTTP
    Teamspeak WebQuery HTTPS
  ```
* Enable the profile by running `sudo ufw allow "<profile_name>"`
  Replacing the `<profile_name>` with the name listed
  ```
  arrorn@server:~/ufwApps$ sudo ufw allow "Valheim"
  Rules updated
  Rules updated (v6)
  ```
* Verify UFW has enabled the specified profile with `sudo ufw status`
  ```
  arrorn@server:~$ sudo ufw status
  Status: active

  To                         Action      From
  --                         ------      ----
  OpenSSH                    ALLOW       Anywhere
  Valheim                    ALLOW       Anywhere
  OpenSSH (v6)               ALLOW       Anywhere (v6)
  Valheim (v6)               ALLOW       Anywhere (v6)

  ```