# Notes
SAP CAPM Notes
================================================================
commands of sap capm:
1. cf apps
2. cf start appname
3. cf scale -i noofinstance(horizontal scaling)
4. cf scale -m noofgb(vertical scaling)
5. cf push appname
================================================================

question:Importance of manifest.yml file in sap btp
ans)The manifest.yml file is important in SAP BTP (especially the Cloud Foundry environment) because it acts as a deployment descriptor, specifying how an application should be deployed, configured, and managed in the cloud.

Purpose and Role:
The file contains key deployment details such as app name, buildpacks, memory allocation, environment variables, services, routes, and other settings.

Using manifest.yml simplifies deployment: instead of supplying configuration flags each time via CLI, you define everything in the file, making deployments consistent and easily reproducible.

Benefits for Projects
It can be tracked in source control, enabling teams to maintain deployment configuration alongside code, supporting collaboration and traceability.

Manifest files support automation and CI/CD pipelines, providing a single source of truth for deployment requirements and reducing manual errors when moving apps between environments.

=============================================================================================================================

Question: what is the difference between cf push and cf push appname
ans)The difference between cf push and cf push APP-NAME in SAP BTP (Cloud Foundry) is in how the app name is determined and how deployments are managed with or without a manifest file.

cf push
When you run just cf push, Cloud Foundry looks for a manifest.yml file in the current directory.

The manifest.yml should contain one or more applications, with their names, configurations, and other deployment parameters.

If the manifest includes multiple apps, cf push will deploy all apps described in the manifest.

If you omit the app name and manifest is missing or incomplete, the command will fail or prompt for info.

cf push APP-NAME
By running cf push APP-NAME, you specify the name of the app directly on the command line.

This overrides any app name given in the manifest and deploys only that app (useful when the manifest describes multiple apps).

Allows push of a single app from a manifest with multiple apps, or from a directory without a manifest, using CLI defaults.

You can tailor deployment using flags and parameters (memory, buildpack, etc.) directly in this CLI command.

Summary
cf push uses the manifest to deploy all listed apps, applying their manifest-defined settings.

cf push APP-NAME deploys just the specified app, using CLI or manifest settings, and ignores other apps in the manifest.

Both commands support additional flags for custom deployments (e.g., cf push APP-NAME -f manifest.yml).

Using just cf push deploys all apps from the manifest file, while cf push APP-NAME deploys only the named app, which is critical in multi-app projects and for targeted updates.
==================================================================================================
   commands to push the table changes to sql lite in capm

   1. cds compile db/db_filename.cds -2 sql -----> this doesnot generates the physical artifact in the database. rather it checks the inconsistenciews .
   2. cds deploy --to sqlite----> actually deploys the artifacts in the database.
study the question what is the difference between cds deploy and cds compile
===================================================================================================
