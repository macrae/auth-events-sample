# auth-events-sample

Synthetic security alerts for a data exercise. No real user data.

## alerts.csv

One row per alert, March–August 2026, with the analyst's verdict.

| Column | Description |
|---|---|
| `alert_id` | Alert identifier |
| `alert_time` | When the alert fired (UTC) |
| `user` | Account name |
| `account_type` | `human` or `service` |
| `department` | Department |
| `office` | Office location, or `Remote` |
| `privileged` | 1 if the account has admin rights |
| `tenure_days` | Days since the account was created |
| `days_until_departure` | Days until the person's last day, if one is scheduled |
| `rule_name` | Detection rule that fired |
| `new_device` | 1 if the device hasn't been seen for this account |
| `new_country` | 1 if the country hasn't been seen for this account |
| `geo_velocity_kmh` | Implied travel speed since the previous login |
| `failed_logins_1h` | Failed logins in the prior hour |
| `hour_unusualness` | 0–1, how unusual the hour is for this account |
| `mfa_method` | Second factor used |
| `asn_type` | Network type of the source IP |
| `ip_reputation` | 0–100, higher is more trusted |
| `logins_24h` | Logins in the prior 24 hours |
| `logins_7d` | Logins in the prior 7 days |
| `distinct_ips_7d` | Distinct source IPs in the prior 7 days |
| `bytes_out_mb` | Data downloaded in the session |
| `session_minutes` | Session length |
| `browser` | Browser family |
| `os` | Operating system |
| `user_agent_length` | Length of the user-agent string |
| `analyst` | Analyst who reviewed the alert |
| `triage_minutes` | Time spent reviewing the alert |
| `verdict` | `true_positive` or `false_positive` |

## Loading

```python
import pandas as pd

alerts = pd.read_csv("alerts.csv")
```
