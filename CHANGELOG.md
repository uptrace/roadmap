# 2022

## Mar 3 2022

Improved metrics UI and added documentation:

- [Querying metrics](https://docs.uptrace.dev/guide/querying-metrics.html)
- [Alerts and notifications](https://docs.uptrace.dev/guide/alerting.html)
- [Timeseries metrics](https://opentelemetry.uptrace.dev/guide/metrics.html)

## Feb 20 2022

Added metrics monitoring and anomaly detection.

## Feb 10 2022

Improved project notification and anomaly detection settings for span groups.

## Jan 25 2022

Added metrics dashboards for
[PostgreSQL](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/postgresqlreceiver),
[MySQL](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/mysqlreceiver),
and
[Kafka](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/kafkametricsreceiver).
That requires OpenTelemetry [Collector](https://opentelemetry.uptrace.dev/guide/collector.html)
v0.43+.

## Jan 15 2022

Added instructions for using [OpenTelemetry Java](https://docs.uptrace.dev/guide/java.html) with
Uptrace.

## Jan 20 2022

Made large metrics dashboards significantly faster.

## Jan 12 2022

Improved Uptrace query builder to support
[nested queries](https://docs.uptrace.dev/guide/querying.html#nested-queries).

## Jan 05 2022

Added 2 new span attributes:

- `span.trace_duration` - the duration of the trace root span.
- `span.trace_group_id` - the group id of the trace root span.

That allows to explore/analyze trace groups instead of individual traces by clicking "Explore trace
groups" button when viewing traces.

Internally, that is implemented by delaying spans processing until the root span is available. If
the root span does not arrive within 24 hours, the whole trace is dropped.
