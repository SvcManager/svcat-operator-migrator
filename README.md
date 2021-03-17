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
Migration tool from SVCAT to SAP BTP Service Operator.

Usage:
  migrate [flags]
  migrate [command]

Available Commands:
  dry-run     Run migration in dry run mode
  help        Help about any command
  run         Run migration process
  version     Prints migrate version

Flags:
  -c, --config string       config file (default is $HOME/.migrate/config.json)
  -h, --help                help for migrate
  -k, --kubeconfig string   absolute path to the kubeconfig file (default $HOME/.kube/config)
  -n, --namespace string    namespace to find operator secret (default sap-btp-operator)
```

