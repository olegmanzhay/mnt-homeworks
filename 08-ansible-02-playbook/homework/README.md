Задание 3
--------------------------
https://github.com/olegmanzhay/mnt-homeworks/tree/MNT-video/08-ansible-02-playbook/homework

После разворачивания  клик нужно сделать следующеe:
- добавить прослушку 0.0.0.0 - чтобы clickhouse принимал все запросы (в том числе от lighthouse)


Установка Vector на тачку clickhouse и сбор Error.log clickhouse
ubuntu@vector:/opt/vector/vector-x86_64-unknown-linux-musl/bin$ ./vector --config-toml /etc/vector/vector.toml
2026-02-19T11:52:43.869332Z  INFO vector::app: Log level is enabled. level="vector=info,codec=info,vrl=info,file_source=info,tower_limit=trace,rdkafka=info,buffers=info,lapin=info,kube=info"
2026-02-19T11:52:43.869863Z  INFO vector::app: Loading configs. paths=["/etc/vector/vector.toml"]
2026-02-19T11:52:43.871633Z  INFO vector::topology::running: Running healthchecks.
2026-02-19T11:52:43.871741Z  INFO vector: Vector has started. debug="false" version="0.30.0" arch="x86_64" revision="38c3f0b 2023-05-22 17:38:48.655488673"
2026-02-19T11:52:43.871762Z  INFO vector::app: API is disabled, enable by setting `api.enabled` to `true` and use commands like `vector top`.
2026-02-19T11:52:43.871858Z  INFO vector::topology::builder: Healthcheck passed.
2026-02-19T11:52:43.871852Z  INFO source{component_kind="source" component_id=clickhouse_logs component_type=file component_name=clickhouse_logs}: vector::sources::file: Starting file server. include=["/var/log/clickhouse-server/clickhouse-server.err.log"] exclude=[]
2026-02-19T11:52:43.872225Z  INFO source{component_kind="source" component_id=clickhouse_logs component_type=file component_name=clickhouse_logs}:file_server: file_source::checkpointer: Loaded checkpoint data.
2026-02-19T11:52:43.872494Z  INFO source{component_kind="source" component_id=clickhouse_logs component_type=file component_name=clickhouse_logs}:file_server: vector::internal_events::file::source: Found new file to watch. file=/var/log/clickhouse-server/clickhouse-server.err.log
{"filename":"/var/log/clickhouse-server/clickhouse-server.err.log","host":"vector","message":"123123123","source_type":"file","timestamp":"2026-02-19T11:54:36.586983927Z"}