## Create Logging Data

```sh
NENTRIES=10 python generate_logs.py > web_server_logs.log
```


## Create Log Group

```sh
aws logs create-log-group --log-group-name "/example/basic/app2"
```


## Set Retention on Log Group

```sh
aws logs put-retention-policy --log-group-name "/example/basic/app2" --retention-in-days 1
```


## Create Log Stream

```sh
aws logs create-log-stream --log-group-name "/example/basic/app2" --log-stream-name $(date +%s)
```

## Describe Log Stream
```sh
aws logs describe-log-streams --log-group-name "/example/basic/app"
```

## Send Logs to Log Stream (Invio di log per applicazioni custom) Inviare il file logs.json allo streamer
aws logs put-log-events --log-group-name "/example/basic/app" --log-stream-name 1744127291  --log-events file://logs.json


## Ruby SDK Logs

```sh
bundle install
bundle exec rake log
```
