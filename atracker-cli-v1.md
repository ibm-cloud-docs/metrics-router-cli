---
 
copyright:
  years:  2021, 2022
lastupdated: "2022-08-12"

subcollection: atracker-cli-plugin

keywords: IBM Cloud Activity Tracker Event Routing CLI, IBM Cloud Activity Tracker Event Routing command line, IBM Cloud Activity Tracker Event Routing terminal, IBM Cloud Activity Tracker Event Routing shell

---

{{site.data.keyword.attribute-definition-list}}

# Activity Tracker Event Routing V1 CLI
{: #atracker-v1-cli}

The {{site.data.keyword.cloud}} command-line interface (CLI) provides extra capabilities for service offerings. This information describes how you can use the CLI to define and manage settings for your {{site.data.keyword.atracker_full}} instance using the V1 CLI.
{: shortdesc}

This information applies only if you use an {{site.data.keyword.at_full}} [Event Routing offering](/docs/atracker?topic=atracker-getting-started). See the [command line references for {{site.data.keyword.at_full}} hosted event search](/docs/activity-tracker-cli-plugin?topic=activity-tracker-cli-plugin-activity-tracker-cli) for the CLI for that offering.
{: important}

The V1 CLI is deprecated. See [Activity Tracker Event Routing V2 CLI](/docs/atracker-cli-plugin?topic=atracker-cli-plugin-atracker-v2-cli) for information on using the V2 CLI.  Also see [migrating resources](/docs/atracker?topic=atracker-migration) for information on migrating from your V1 configuration.
{: deprecated}

## Prerequisites
{: #atracker-v1-cli-prereq}

* Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* Install the CLI by running the following command:

   ```sh
   ibmcloud plugin install atracker
   ```
   {: pre}

You're notified on the command line when updates to the {{site.data.keyword.cloud_notm}} CLI and plug-ins are available. Be sure to keep your CLI up to date so that you can use the latest commands. You can view the current version of all installed plug-ins by running `ibmcloud plugin list`.
{: tip}

## ibmcloud atracker route create
{: #route-create-v1-cli}

Use this command to create a new route for an {{site.data.keyword.atracker_full_notm}} target in a region. 

```sh
ibmcloud atracker route create --name <ROUTE_NAME> --target <TARGET> [--receive-global-events] [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #route-create-v1-options}

`--target <TARGET_ID>`
:   The ID or name of the target.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--name <ROUTE_NAME>`
:   The name to be given to the route.

    Do not include any personal identifying information (PII) in any resource names.
    {: important}

`--receive-global-events`
:   Specifies that the route will receive [global events](/docs/atracker?topic=atracker-event_types#event_types_global).  If not specified, global events will not be sent on the route

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker route update
{: #route-update-v1-cli}

Use this command to update a route for an {{site.data.keyword.atracker_full_notm}} target in a region.  Any specified value that is different from when the route was originally created will be updated to the value specified in the command.

```sh
ibmcloud atracker route update --route <ROUTE> [--name <ROUTE_NAME>] [--receive-global-events ( TRUE | FALSE )] [--target <TARGET>] [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #route-update-v1-options}

`--route <ROUTE>`
:   The name or ID of the route to be updated.

`--target <TARGET>`
:   The ID or name of the target.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--name <ROUTE_NAME>`
:   The name to be given to the route.

    Do not include any personal identifying information (PII) in any resource names.
    {: important}

`--receive-global-events (TRUE | FALSE)`
:   Specifies that the route will receive [global events](/docs/atracker?topic=atracker-event_types#event_types_global).  If not specified, global events will not be sent on the route

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker route rm
{: #route-delete-v1-cli}

Use this command to delete a route for an {{site.data.keyword.atracker_full_notm}} region. 

```sh
ibmcloud atracker route rm --route <ROUTE> [--region <REGION>] [--force]
```
{: pre}

### Command options 
{: #route-rm-v1-options}

`--route <ROUTE>`
:   The name or ID of the route to be deleted.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--force`
:   Will delete the route without providing the user with any additional prompt.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker route get
{: #route-view-v1-cli}

Use this command to get information about a route for an {{site.data.keyword.atracker_full_notm}} region. 

```sh
ibmcloud atracker route get --route [ <ROUTE_ID> | <ROUTE_NAME> ] [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #route-get-v1-options}

`--route <ROUTE_ID>` | `<ROUTE_NAME>`
:   The route ID or name of the route.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker route ls
{: #route-list-v1-cli}

Use this command to list all the configured routes for a specific {{site.data.keyword.atracker_full_notm}} region or all {{site.data.keyword.atracker_full_notm}} regions. 

```sh
ibmcloud atracker route ls [--region <REGION> | --all-regions ] [--output JSON]
```
{: pre}

### Command options 
{: #route-ls-v1-options}

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--all-regions`
:   Specifies the routes for all regions should be listed.  This option cannot be specified if `--region` is specified.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker target create
{: #target-create-v1-cli}

Use this command to create an {{site.data.keyword.atracker_full_notm}} service target to be used to configure a destination for activity events.

```sh
 ibmcloud atracker target create --name <TARGET_NAME> --type <TARGET_TYPE> ( --file <COS_ENDPOINT_DEFINITION_JSON_FILE> |  --endpoint <COS_ENDPOINT> --bucket <COS_BUCKET> --target-crn <COS_TARGET_CRN> --api-key ( <COS_API_KEY> | <@COS_API_KEY_FILE> ) ) [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #target-create-v1-options}

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--name <TARGET_NAME>`
:   The name to be given to the target.

    Do not include any personal identifying information (PII) in any resource names.
    {: important}

`--type <TARGET_TYPE>`
:   Only supported value for `<TARGET_TYPE>` is `cloud-object-storage`.

`--file <@COS_ENDPOINT_DEFINITION_JSON_FILE>`
:   A file containing an endpoint definition in the following format:

    ```json
    {
      "endpoint": "aaaaa", 
      "target_crn": "yyyyy",
      "bucket": "zzzzzz", 
      "api_key": "xxxxxx"
    }
    ```
    {: codeblock}

`--endpoint <COS_ENDPOINT>`
:   The {{site.data.keyword.cos_full_notm}} endpoint to be associated with the {{site.data.keyword.cos_full_notm}} bucket.

`--bucket <BUCKET>`
:    The name of the {{site.data.keyword.cos_full_notm}} bucket to be associated with the target.

`--target-crn <COS_TARGET_CRN>`
:   The CRN of the {{site.data.keyword.cos_full_notm}} instance.

`--api-key <COS_API_KEY>` | `<@COS_API_KEY_FILE>`
:   Your [API key](/docs/account?topic=account-manapikey) value or a reference to the API Key file used when logging in.  For example, `ibmcloud login --apikey $KEYFILE`

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker target update
{: #target-update-v1-cli}

Use this command to update a target for an {{site.data.keyword.atracker_full_notm}} region.  Any specified value that is different from when the target was originally created will be updated to the value specified in the command.

```sh
ibmcloud atracker target update --target <TARGET> [--name <TARGET_NAME>] [ --file <COS_ENDPOINT_DEFINITION_JSON_FILE> |  [--endpoint <COS_ENDPOINT>] [--bucket <COS_BUCKET>] [--target-crn <COS_TARGET_CRN>] [--api-key ( <COS_API_KEY> | <@COS_API_KEY_FILE> )] ) ] [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #target-update-v1-options}

`--target <TARGET>`
:   The ID or current target name.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--name <TARGET_NAME>`
:   The name to be given to the target.

    Do not include any personal identifying information (PII) in any resource names.
    {: important}

`--file <@COS_ENDPOINT_DEFINITION_JSON_FILE>`
:   A file containing an endpoint definition in the following format:

    ```json
    {
      "endpoint": "aaaaa", 
      "target_crn": "yyyyy",
      "bucket": "zzzzzz", 
      "api_key": "xxxxxx"
    }
    ```
    {: codeblock}

`--endpoint <COS_ENDPOINT>`
:   The {{site.data.keyword.cos_full_notm}} endpoint to be associated with the {{site.data.keyword.cos_full_notm}} bucket.

`--bucket <COS_BUCKET>`
:   The name of the {{site.data.keyword.cos_full_notm}} bucket to be associated with the target.

`--target-crn <COS_TARGET_CRN>`
:   The CRN of the {{site.data.keyword.cos_full_notm}} instance.

`--api-key <COS_API_KEY>` | `<@COS_API_KEY_FILE>`
:   Your [API key](/docs/account?topic=account-manapikey) value or a reference to the API Key file used when logging in.  For example, `ibmcloud login --apikey $KEYFILE`

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker target rm
{: #target-delete-v1-cli}

Use this command to delete a target for an {{site.data.keyword.atracker_full_notm}} region. 

```sh
ibmcloud atracker target rm --target <TARGET> [--region <REGION>] [--force]
```
{: pre}

### Command options 
{: #target-rm-v1-options}

`--target <TARGET>`
:   The ID or name of the target.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--force`
:   Will delete the target without providing the user with any additional prompt.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker target validate
{: #target-validate-v1-cli}

Use this command to validate that a target is correctly configured for an {{site.data.keyword.atracker_full_notm}} region. 

```sh
ibmcloud atracker target validate --target <TARGET> [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #target-validate-v1-options}

`--target <TARGET>`
:   The ID or name of the target.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker target get
{: #target-get-v1-cli}

Use this command to get information about a target for an {{site.data.keyword.atracker_full_notm}} region. 

```sh
ibmcloud atracker target get --target <TARGET> [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #target-get-v1-options}

`--target <TARGET>`
:   The ID or name of the target.

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker target ls
{: #target-list-v1-cli}

Use this command to list the configured targets for an {{site.data.keyword.atracker_full_notm}} region.

```sh
ibmcloud atracker target ls [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #target-v1-options}

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker endpoint api ls
{: #endpoints-manage-list-v1-cli}

Use the following command to list the {{site.data.keyword.atracker_full_notm}} service API endpoints.

```sh
ibmcloud atracker endpoint api ls [--output JSON]
```
{: pre}

### Command options 
{: #endpoint-ls-v1-options}

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker endpoint api get
{: #endpoints-manage-get-v1-cli}

You can use the following command to get information about the public and private endpoints that are enabled in a region when you use the {{site.data.keyword.atracker_full_notm}}:

```sh
ibmcloud atracker endpoint api get [--region <REGION>] [--output JSON]
```
{: pre}

### Command options 
{: #endpoint-get-v1-options}

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker endpoint api update --public-enabled FALSE
{: #endpoints-manage-disable-v1-cli}

You can disable public endpoints per region in your account.

You can use the following command to disable a public endpoint in a region:

```sh
ibmcloud atracker endpoint api update --public-enabled FALSE [--region <REGION>] [--output JSON] [--force]
```
{: pre}

Before disabling a public endpoint (`--public-enabled FALSE`), make sure your account has access to the private endpoint.  You can do this by running the command `bx account show`.  If `VRF Enabled` is `true` and `Service Endpoint Enabled` is `true` then you have access to the private endpoint.  If you do not have access to the private endpoint, you will be unable to re-enable the public endpoint since private endpoint access is required to re-enable the public endpoint.
{: important}

### Command options 
{: #endpoint-update-v1-disable}

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`--force`
:   The command will be run without prompting the user whether or not to continue with the command.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker endpoint api update --public-enabled TRUE
{: #endpoints-manage-update-v1-cli}

You can configure for each region the availability of public endpoints so that you can configure {{site.data.keyword.atracker_full_notm}} resources in your account.

You can use the following command to enable a public endpoint in a region:

```sh
ibmcloud atracker endpoint api update --public-enabled TRUE [--region <REGION>] [--output JSON] [--force]
```
{: pre}

You must have access to a private endpoint to enable a public endpoint. 
{: important}

### Command options 
{: #endpoint-update-v1-enable}

`--region <REGION>` | `-r <REGION>`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output JSON`
:   If specified, output will be returned in JSON format.  If `JSON` is not specified, output will be returned in a tabular format.

`--force`
:   The command will be run without prompting the user whether or not to continue with the command.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud atracker config report
{: #route-report-v1-running}

Use the following command to return a report about the {{site.data.keyword.atracker_full_notm}} service configuration.  This report will include any issues in the configuration. 

```text
ibmcloud atracker config report --output YAML 
```
{: pre}

