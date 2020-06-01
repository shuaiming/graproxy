# graproxy
simple implementation for grafana auth.proxy with openid

**DEPRECATED** USE Grafana OAuth Authentication

## grafana config example

    [auth.proxy]
    enabled = true
    header_name = X-WEBAUTH-USER
    header_property = email
    auto_sign_up = true


## usage

    Usage of ./graproxy:
      -cert string
          ssl server certificate file (default "ssl/server.crt")
      -endpoint string
          openid endpoint
      -grafana string
          grafana host and port (default "http://127.0.0.1:3000")
      -key string
          ssl server key file (default "ssl/server.key")
      -l string
          proxy server listen address (default ":8080")
      -n string
          proxy domain name openid will return to (default "localhost")
      -ssl
          enable https

## living example

    ./graproxy -endpoint "https://login.provider.com/openid" -grafana "http://127.0.0.1:3000" -ssl -l "0.0.0.0:8443" -n monitor.example.com


## build

    cd src && go build -o ~/graproxy
