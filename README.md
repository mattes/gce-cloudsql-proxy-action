# Google Cloud SQL Proxy

Github action which will start a [Google Cloud SQL Proxy](https://cloud.google.com/sql/docs/postgres/sql-proxy) as Docker container. 

## Prerequisites

Set up the following resources manually in the Cloud Console 
or use a tool like [Terraform](https://www.terraform.io).

* Running Cloud SQL instance with a public IP address
* Create Service Account with Role `Cloud SQL Client` and export a new JSON key.


## Github Action Inputs

| Variable                         | Description                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| `creds`                          | ***Required*** Service Account JSON Key (not base64 encoded)                |
| `instance`                       | ***Required*** Cloud SQL connection name                                    |
| `port`                           | Listen on port, default 5432                                                |
| `proxy_version`                  | Cloud SQL Proxy version, default 1.21.0                                     |


## Example Usage

```
uses: mattes/gce-cloudsql-proxy-action@v1
with:
  creds: ${{ secrets.GOOGLE_APPLICATION_CREDENTIALS }}
  instance: my-project:us-central1:instance-1
```

