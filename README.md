# svcat-operator-migrator


## Getting started

To use the migration CLI you need to download and install it first:

### Approach 1: Manual installation

#### Download CLI
`` go get github.com/SvcManager/svcat-operator-migrator``

#### Install CLI

``go install github.com/SvcManager/svcat-operator-migrator``

#### Rename the CLI binary

``mv $GOPATH/bin/svcat-operator-migrator $GOPATH/bin/migrate``

### Approach 2: Get the latest CLI release
You can get started with the CLI by simply downloading the latest release from [HERE](https://github.com/SvcManager/svcat-operator-migrator/releases).


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

