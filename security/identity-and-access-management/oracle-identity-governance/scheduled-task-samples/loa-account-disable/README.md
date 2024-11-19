# Leave Of Absence Account Disable Scheduled Task

This asset contains the code and deployment items for a scheduled task designed to disable all active accounts of Oracle Identity Governance users until a certain date value is reached, and the accounts are re-enabled. The data value is stored either in a Date-type UDF (User-defined field) or pre-existing user attribute. Out of the box date fields can also be used since the field name storing the data value can be specified as a scheduler parameter.

Can be used as a basis to demonstrate an alternative "leave of absence" implementation, where the users in question can still log into Oracle Identity Governance, to, for example, participate in approval processes or delegate their rights to a proxy, however they aren't able to access any of the downstream systems for which they have accounts provisioned by Oracle Identity Governance while the LOA is in effect.

Developed on and compatible with OIG 11g R2 PS3 and above.

Review Date: 28.10.2024

# When to use this asset?

When there's a need to provide or demonstrate the functionality described above or something similar, which can be adapted from the provided code.

# How to use this asset?

## Building and deployment

Here's a short build and deployment checklist:

1. Generate a jar file containing the sample code.
2. Upload the jar file to an OIG environment using OIG's command line "Jar Upload" utility.
3. Use the Enterprise Manager web interface to upload the scheduled task metadata/definition into the MDS repository.
4. Create a scheduled task in OIG based on the uploaded definition.

Please see the useful link below for detailed build and deployment steps.

## Executing the scheduled task

- Ensure you have specified a relevant value for the `LOA end date user attribute` scheduler parameter field in the scheduled task definition. Note that a either a UDF (User-defined field) or a pre-existing user attribute can be used. This value needs to contain the attribute's display label, not the backend name (e.g., `User Login`, not `USR_LOGIN`).

- [Consult this section](https://docs.oracle.com/en/middleware/idm/identity-governance/12.2.1.4/omusg/managing-jobs-1.html#GUID-71BB3623-AEE2-4F64-BBD4-D921DCA39D7C) on how to manually start or schedule a job.

# Useful Links

[Oracle Identity Governance developer's guide - Developing scheduled tasks](https://docs.oracle.com/en/middleware/idm/identity-governance/12.2.1.4/omdev/developing-scheduled-tasks.html#GUID-F62EF833-1E70-41FC-9DCC-C1EAB407D151)

# License

Copyright (c) 2024 Oracle and/or its affiliates.

Licensed under the Universal Permissive License (UPL), Version 1.0.

See [LICENSE](https://github.com/oracle-devrel/technology-engineering/blob/main/LICENSE) for more details.
