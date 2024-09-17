# Catcher

Wery basic utility server that listen port for incoming POST requests.
Serves for webhooks handling from Docker Hub.

After receiving request, invokes `callback_url` and runs `command`.

```
usage: catcher [-h] -c COMMAND [-p PORT] [--silent] [--detailed-logs]

Listens a specified port for POST requests to catch webhooks from Docker Hub. A valid webhook will trigger the execution of a specified command.

optional arguments:
  -h, --help            show this help message and exit
  -c COMMAND, --command COMMAND
                        Command that should be executed on hook
  -p PORT, --port PORT  Port to listen for incoming hooks
  --silent              Service will produce no logs
  --detailed-logs       Service will produce detailed logs
```
