# auth-events-sample

Synthetic login events for a data exercise. No real user data.

## Files

| File | Contents |
|---|---|
| `auth_events.csv` | One row per login event, one week of activity |
| `users.csv` | One row per employee |

## auth_events.csv

| Column | Description |
|---|---|
| `event_id` | Event identifier |
| `event_time` | When the event happened |
| `source` | System that logged the event (`okta`, `vpn`) |
| `user` | Account name |
| `src_ip` | Source IP address |
| `geo_city` | City from IP lookup |
| `geo_country` | Country code from IP lookup |
| `device_id` | Device identifier |
| `app` | Application signed into |
| `result` | `SUCCESS` or `FAILURE` |
| `failure_reason` | Reason for a failed login |

## users.csv

| Column | Description |
|---|---|
| `user` | Account name |
| `department` | Department |
| `office` | Office location, or `Remote` |
| `hire_date` | Start date |
| `termination_date` | Last day, if leaving |

## Loading

```python
import pandas as pd

events = pd.read_csv("auth_events.csv")
users = pd.read_csv("users.csv")
```
