### Install MongoDB with Homebrew

```bash
`brew install mongodb
mkdir -p /data/db
```
`### Set permissions for the data directory
Ensure that user account running mongod has correct permissions for the directory:

```bash
`sudo chmod 0755 /data/db
sudo chown $USER /data/db
```
`
### Run MongoDB!
iTerm buffer 1: `mongod`  
iTerm buffer 2: `mongo`

---

**Note:** If you get something like this:
```bash
`exception in initAndListen: 10309 Unable to create/open lock file: /data/db/mongod.lock errno:13 Permission denied Is a mongod instance already running?, terminating
```
`
It means that `/data/db` lacks required permission and ownership.

Run `ls -ld /data/db/`

Output should look like this (`gibber` is directory owner and `wheel` is group to which gibber belongs):
```bash
`drwxr-xr-x  7 gibber  wheel  238 Aug  5 11:07 /data/db/
```
`