---
aliases: 
created: 2022-01-20, 9:39:09 am (Thursday, January 20th)
updated: 2022-01-20, 1:04:32 pm (Thursday, January 20th)
---
A CLI for confluent.

## Quirks
**NOTE:** I found out this happened because I was trying to install the components on my local machine even though the confluent platform was setup in a docker container.

When installing components via `confluent-hub install` you *need* to provide `--component-dir` and `--worker-configs`.

- `component-dir` can be any local dir that the user has access to.
    - It's to store whatever you download
        - e.g. `/opt/connectors` -- Don't forget to `chown` so you own the file
- `worker-configs` should point to configuration files for the script to update with the component-dir path
    - If using w/ Kafka, look in the directory where Kafka's code is in for a file `connect-*.properties` file
        - e.g. if you downloaded the tar of kafka, you can find it in `~/Downloads/kafka/config/connect-standalone.properties`


Installing a component after running the service via `docker-compose up` caused some problems.
`broker` and `connect` both exited with statuses of 137