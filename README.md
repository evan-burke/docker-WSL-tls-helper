
WORK IN PROGRESS - instead of specifying server/client on command line, automatically place TLS certs in appropriate directories for use with Docker client running within WSL, connecting to a local instance of Docker for Windows. 


# frntn/docker-tls-helper

One command to generate the numerous certificates and keys required to [protect the Docker daemon socket](https://docs.docker.com/engine/security/https/).

## Usage

Setup `SRV_SUBJ` and `CLT_SUBJ` environment variables and execute the script :

```bash
curl -sSL https://raw.githubusercontent.com/frntn/docker-tls-helper/master/dockertls.sh | SRV_SUBJ="/CN=remote.example.com" CLT_SUBJ="/CN=Docker Admin CLI" bash
```

You can additionally Setup `SRV_SAN` environment variable to access your docker server from multiple endpoints :

```bash
curl -sSL https://raw.githubusercontent.com/frntn/docker-tls-helper/master/dockertls.sh | SRV_SAN="DNS:docker.example.com,IP:1.1.1.1,IP:2.2.2.2" SRV_SUBJ="/CN=remote.example.com" CLT_SUBJ="/CN=Docker Admin CLI" bash
```

## Result

Here is a screenshot of the generated ouput :

![official-logo](img/result.png?raw=true)

