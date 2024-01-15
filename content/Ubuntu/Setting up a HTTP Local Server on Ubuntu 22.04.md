---
Reference: https://askubuntu.com/questions/1102594/how-do-i-set-up-the-simplest-http-local-server
---
To start the http server on port _port_ simply type:

```bash
python -m http.server port
```

If you want to share files and directories, `cd` in to whatever directory you want to serve:

```bash
cd /my/html/files
python -m http.server 8080
```

Should you want to use an address other than the default `0.0.0.0` you can use `--bind`

Ex: `python -m http.server 8080 --bind 127.0.0.1` will serve them at the address `127.0.0.1:8080`

