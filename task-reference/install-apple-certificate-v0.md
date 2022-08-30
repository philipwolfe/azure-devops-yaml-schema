---
title: InstallAppleCertificate@0 - Install Apple Certificate v0 task
description: Install an Apple certificate required to build on a macOS agent (task version 0).
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# InstallAppleCertificate@0 - Install Apple Certificate v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Install an Apple certificate required to build on a macOS agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Install Apple Certificate v0
# Install an Apple certificate required to build on a macOS agent.
- task: InstallAppleCertificate@0
  inputs:
    certSecureFile: # string. Required. Certificate (P12). 
    #certPwd: # string. Certificate (P12) Password. 
  # Advanced
    keychain: 'temp' # 'default' | 'temp' | 'custom'. Required. Keychain. Default: 'temp'.
    #keychainPassword: # string. Keychain Password. 
    #customKeychainPath: # string. Required when keychain = custom. Custom Keychain Path. 
    #deleteCert: # boolean. Optional. Use when keychain = custom || keychain = default. Delete Certificate from Keychain. 
    #deleteCustomKeychain: # boolean. Optional. Use when keychain = custom. Delete Custom Keychain. 
    #signingIdentity: # string. Certificate Signing Identity.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="certSecureFile"::: -->
:::moniker range="<=azure-pipelines"

**`certSecureFile`** - **Certificate (P12)**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the certificate (.p12) that was uploaded to `Secure Files` to install on the macOS agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certPwd"::: -->
:::moniker range="<=azure-pipelines"

**`certPwd`** - **Certificate (P12) Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to the Apple certificate (.p12). Use a new build variable with its lock enabled on the `Variables` tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keychain"::: -->
:::moniker range="<=azure-pipelines"

**`keychain`** - **Keychain**<br>
Type: string. Required. Allowed values: 'default', 'temp', 'custom'. Default value: 'temp'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the keychain in which to install the Apple certificate. A temporary keychain will always be deleted after the build or release is complete.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keychainPassword"::: -->
:::moniker range="<=azure-pipelines"

**`keychainPassword`** - **Keychain Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to unlock the keychain. Use a new build variable with its lock enabled on the `Variables` tab to encrypt this value. A password is generated for the temporary keychain if not specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customKeychainPath"::: -->
:::moniker range="<=azure-pipelines"

**`customKeychainPath`** - **Custom Keychain Path**<br>
Type: string. Required when keychain = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Full path to a custom keychain file. The keychain will be created if it does not exist.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteCert"::: -->
:::moniker range="<=azure-pipelines"

**`deleteCert`** - **Delete Certificate from Keychain**<br>
Type: boolean. Optional. Use when keychain = custom || keychain = default.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select to delete the certificate from the keychain after the build or release is complete.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteCustomKeychain"::: -->
:::moniker range="<=azure-pipelines"

**`deleteCustomKeychain`** - **Delete Custom Keychain**<br>
Type: boolean. Optional. Use when keychain = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select to delete the custom keychain from the agent after the build or release is complete.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Certificate Signing Identity**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Common Name of the subject in the signing certificate.  Will attempt to parse the Common Name if this is left empty.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: xcode |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.116.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->