# Hikvision Data Extractor

Hikvision camera systems come with a clunky web interface as the sole method to consult the captured data.

This script goes through authentication and search to export the data it holds.

| Configuration parameter | Description
| --- | ---
| host | Target server, including port (ex.: `1.1.1.1:80`)
| username / password | Account used on web app
| searchQueryPageSize | # of results to fetch per request (default 50)
| searchRangeDaysBack | # of days in the past to fetch results for (default 14 days)
| tracks | Array of camera identifiers to fetch results for. Useful when the system is composed of multiple cameras, yet still required when there's only one (ex.: `[101]`)

Sample output:

| Track | Timestamp | LicensePlate | ImageUrl
| --- | --- | --- | ---
| 101 | 2023-03-21T06:49:09Z | 2AUB629 | http://{host}/picture/...
| 101 | 2023-03-21T06:49:14Z | 1REV344 | http://{host}/picture/...
| 101 | 2023-03-21T06:50:35Z | 2DPO903 | http://{host}/picture/...
| 101 | 2023-03-21T06:52:40Z | 2MIR821 | http://{host}/picture/...