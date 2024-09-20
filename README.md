# Ashton

The webhook catcher utility

### Description

Listens on a specified `--port` for POST requests to catch a webhooks. Webhook request could include a `--signature-header`, than `--secret` required to lavidate payload. A valid webhook triggers the execution of a specified commands. `--pre-command` and `--post-command` are executed before and after the `--command` respectively (suitable for webhook callback). Commands will get payload as an argument unless `--ignore-payload` specified. Command failure won't interrupt sequence! Arguments can be specified in a file provided by `--env-file`. Command-line arguments will take precedence over those from the file

### Usage
```
ashton -p PORT -c COMMAND [--env-file ENV_FILE] [-s SECRET] [--signature-header SIGNATURE_HEADER] [--pre-command PRE_COMMAND] [--post-command POST_COMMAND] [--ignore-payload] [--silent] [--detailed-logs] [-h]

options:
  -p PORT, --port PORT  [REQUIRED] Port to listen for incoming hooks
  -c COMMAND, --command COMMAND
                        [REQUIRED] Command that will be executed by webhook
  --env-file ENV_FILE   File with arguments specified in KEY=VALUE format
  -s SECRET, --secret SECRET
                        Secret to validate webhook sha256 signature
  --signature-header SIGNATURE_HEADER
                        Header that contains sha256 signature
  --pre-command PRE_COMMAND
                        Command that should be executed before COMMAND
  --post-command POST_COMMAND
                        Command that should be executed after COMMAND
  --ignore-payload      Commands won't receive payload as an argument
  --silent              Service will produce no logs
  --detailed-logs       Service will produce detailed logs
  -h, --help            show this help message and exit
```

## Licence
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <https://unlicense.org>