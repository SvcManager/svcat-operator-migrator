# svcat-operator-migrator


## Getting started

To use the migration CLI you need to download and install it first:

### Approach 1: Manual installation

#### Download CLI
`` go get github.wdf.sap.corp/SvcManager/k8s-migrator``

#### Install CLI

``go install github.wdf.sap.corp/SvcManager/k8s-migrator``

#### Rename the CLI binary

``mv $GOPATH/bin/k8s-migrator $GOPATH/bin/migrate``


## Using CLI

```
migrate from SVCAT to SAP BTP Service Operator.

Usage:
  migrate [flags]
  migrate [command]

Available Commands:
  help        Help about any command
  run         Run migration process

Flags:
      --config string       config file (default is $HOME/.migrate/config.json)
  -h, --help                help for migrate
      --kubeconfig string   absolute path to the kubeconfig file (default $HOME/.kube/config)
  -n, --namespace string    namespace to find operator secret (default sap-btp-operator)

Use "migrate [command] --help" for more information about a command.
```

