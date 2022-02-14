# hello-operator



## Environment

### minikube

```shell
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version
minikube version: v1.25.1
commit: 3e64b11ed75e56e4898ea85f96b2e4af0301f43d

sudo usermod -aG docker $USER && newgrp docker

minikube start
```

### operaror-sdk

https://sdk.operatorframework.io/docs/installation/

```shell
export ARCH=$(case $(uname -m) in x86_64) echo -n amd64 ;; aarch64) echo -n arm64 ;; *) echo -n $(uname -m) ;; esac)
export OS=$(uname | awk '{print tolower($0)}')
export OPERATOR_SDK_DL_URL=https://github.com/operator-framework/operator-sdk/releases/download/v1.17.0
curl -LO ${OPERATOR_SDK_DL_URL}/operator-sdk_${OS}_${ARCH}

chmod +x operator-sdk_${OS}_${ARCH} && sudo mv operator-sdk_${OS}_${ARCH} /usr/local/bin/operator-sdk
operator-sdk version
operator-sdk version: "v1.17.0", commit: "704b02a9ba86e85f43edb1b20457859e9eedc6e6", kubernetes version: "1.21", go version: "go1.17.6", GOOS: "linux", GOARCH: "amd64"
```



