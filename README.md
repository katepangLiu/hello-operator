# hello-operator



## Environment

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



## Build operator

### operator-sdk

#### Generate boilerplate

```shell
mkdir -p develop/operator/hello-operator
go mod init hello-operator

operator-sdk init
```

#### Create APIs

```shell
operator-sdk create api --group <group> --version <version> --kind <ResourceKind>
```



### Coding

#### Resource



#### Controller 



## Run operator

### Run locally outside the cluster

```shell
make install
```



### Run as a Deployment inside the cluster

```shell
make deploy
```

```shell
kubectl get all -A |grep hello

hello-operator-system   pod/hello-operator-controller-manager-864d6984fb-6g9dr   0/2     ContainerCreating   0          19s
hello-operator-system   service/hello-operator-controller-manager-metrics-service   ClusterIP   10.96.2.75   <none>        8443/TCP                 19s
hello-operator-system   deployment.apps/hello-operator-controller-manager   0/1     1            0           19s
hello-operator-system   replicaset.apps/hello-operator-controller-manager-864d6984fb   1         1         0       19s
```



### Deploy your Operator with OLM

*TODO*

