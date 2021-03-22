# svcat-operator-migrator

## Prerequisite
1. Prepare your platform for migration by executing: </br>
```smctl curl -X PUT  -d '{"sourcePlatformID": ":platformID"}' /v1/migrate/service_operator/:instanceID``` </br>
**instanceID**: instance of service-manager/service-operator-access
2. Install [sap btp service operator](https://github.com/SAP/sap-btp-service-operator#setup) by providing clusterID the same as of SVCAT 

***Note: you can delete the old platform after successful migration, as it suspended and not usable anymore***

## Getting started

To use the migration CLI you need to download and install it first:

### Approach 1: Manual installation

#### Download CLI
``go get github.com/SvcManager/svcat-operator-migrator``

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

## Example usage of CLI:

```sh
# Run migration including pre migration validations
> migrate run
Migrator initialized with cluster ID '2b8c7218-2aac-4e77-b936-2bdc7836c175'
*** Fetched 4 instances from SM
*** Fetched 8 bindings from SM
*** Fetched 5 svcat instances from cluster
*** Fetched 9 svcat bindings from cluster
*** Preparing resources
svcat instance name 'test11' id 'XXX-6134-4c89-bff5-YYY' (test11) not found in SM, skipping it...
svcat binding name 'test5' id 'XXX-5226-42cc-81e5-YYY' (test5) not found in SM, skipping it...
*** found 4 instances and 8 bindings to migrate
*** Validating
svcat instance 'dembele' in namespace 'test' was validated successfully
svcat instance 'iniesta' in namespace 'test' was validated successfully
svcat instance 'messi' in namespace 'test' was validated successfully
svcat instance 'pedri' in namespace 'test' was validated successfully
svcat binding 'dembele-binding1' in namespace 'test' was validated successfully
svcat binding 'dembele-binding2' in namespace 'test' was validated successfully
svcat binding 'iniesta-binding1' in namespace 'test' was validated successfully
svcat binding 'iniesta-binding2' in namespace 'test' was validated successfully
svcat binding 'messi-binding1' in namespace 'test' was validated successfully
svcat binding 'messi-binding2' in namespace 'test' was validated successfully
svcat binding 'pedri-binding1' in namespace 'test' was validated successfully
svcat binding 'pedri-binding2' in namespace 'test' was validated successfully
*** Validation completed successfully
migrating service instance 'dembele' in namespace 'test' (smID: '1804a051-bad5-408b-bb4e-ac54c137828a')
instance migrated successfully
migrating service instance 'iniesta' in namespace 'test' (smID: '542f9252-c9ee-47be-b3b9-8db874251a68')
instance migrated successfully
migrating service instance 'messi' in namespace 'test' (smID: '24aa41e5-20e2-4892-ab6c-d74a280f8421')
instance migrated successfully
migrating service instance 'pedri' in namespace 'test' (smID: '7b497532-0dfd-448f-b66b-efbe2701e829')
instance migrated successfully
migrating service binding 'dembele-binding1' in namespace 'test' (smID: '9899e33c-48fc-4025-9dbb-22e34feec93e')
binding migrated successfully
migrating service binding 'dembele-binding2' in namespace 'test' (smID: '52d305e7-4875-41c0-ab65-5930a4f587e4')
binding migrated successfully
migrating service binding 'iniesta-binding1' in namespace 'test' (smID: 'c8b27b9d-2bd3-4e43-a7cd-797001ead68c')
binding migrated successfully
migrating service binding 'iniesta-binding2' in namespace 'test' (smID: 'b8de63d5-3452-4f49-a1d1-d3c223c68ab4')
binding migrated successfully
migrating service binding 'messi-binding1' in namespace 'test' (smID: '41498e3c-215e-4d3a-a38e-e83f442c1d50')
binding migrated successfully
migrating service binding 'messi-binding2' in namespace 'test' (smID: 'c7a43cdc-5e33-40e2-82f7-85ed2545c24f')
binding migrated successfully
migrating service binding 'pedri-binding1' in namespace 'test' (smID: '5a6d6a38-2d17-4a7a-b2dd-2ec88ebabf6d')
binding migrated successfully
migrating service binding 'pedri-binding2' in namespace 'test' (smID: '49bb6994-338e-405b-90f1-74bee3ce48bc')
binding migrated successfully
*** Migration completed successfully

```

