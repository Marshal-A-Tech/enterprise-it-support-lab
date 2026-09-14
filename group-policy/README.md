# Group Policy

## Overview

This section documents the Group Policy configuration and troubleshooting completed in the Enterprise IT Support Lab.

## GPO Configuration

### HR-Drive-Mapping

- GPO Name: HR-Drive-Mapping
- Linked OU: HR Users OU
- Drive Letter: H:
- Shared Folder: \\DC01\HR2
- Action: Update
- Drive Label: HR Shared Drive

## Configuration Path

The drive mapping was configured using:

User Configuration → Preferences → Windows Settings → Drive Maps

The drive map was configured to automatically provide HR users with access to the HR shared folder.

## Group Policy Verification

The applied Group Policy configuration was verified using:

    gpresult /r

The HR-Drive-Mapping GPO was successfully applied to the HR user.

The H: drive appeared on the client workstation and provided access to:

    \\DC01\HR2

## GPO Troubleshooting

A deliberate GPO failure was created by disabling the GPO link.

The following command was used to investigate the applied policies:

    gpresult /r

The HR-Drive-Mapping GPO appeared as filtered because the GPO link was disabled.

The existing H: drive mapping remained on the workstation because the Drive Map action was configured as Update.

## Resolution

The Drive Map action was temporarily changed from Update to Delete.

After Group Policy was reapplied, the existing H: drive mapping was removed.

The Drive Map action was then restored to Update.

After Group Policy was reapplied again, the H: drive was successfully mapped to:

    \\DC01\HR2

## Troubleshooting Flow

SYMPTOM → HR drive mapping did not behave as expected

INFORMATION GATHERING → Checked GPO application using gpresult

HYPOTHESIS → GPO link status and Drive Map action were affecting the existing mapping

TEST → Disabled the GPO link and verified the resulting policy status

ROOT CAUSE → The Update action does not remove an existing drive mapping when the GPO is disabled

FIX → Used the Delete action to remove the existing mapping, then restored Update

VERIFY → Confirmed the H: drive was successfully mapped to the HR shared folder
