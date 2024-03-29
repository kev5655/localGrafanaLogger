# Local Grafana Logger

This Repo is for transform log output of local Terminal logs to Grafana for better filtering and searching on the log stream.

### Install

Run the docker compose file. The docker compose file is for running Grafana, Loki and Promtail.
`docker compose up`

Prepare your logging file

```bash
sudo touch /var/log/<your_log_filename>.log
sudo chmod 666 /var/log/<your_log_filename>.log
```

### Run

Go to your Project and run your command

```bash
<your_command> >> /var/log/<your_log_filename>.log 2>> /var/log/<your_log_filename>.log
# Example
npm run start >> /var/log/fidentity-server.log 2>> /var/log/fidentity-server.log
```

The double `>>` appends logs add the log file, if you want to overwrite the log file you only have to use a `>`.

When you want the log output also in a Terminal run this

`tail -f /var/log/<your_log_filename>.log`

**Look at the Logs**

Open your Grafana on `https://localhost:3000` and Log in with this credentials

Username: admin

Password: admin

### Grafana

[Loki Query how filter log stream](https://grafana.com/docs/loki/latest/logql/log_queries/)
