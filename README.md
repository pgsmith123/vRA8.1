# vRA8.1
This codeset provides the capability to deploy multiple unique disks to a VM during the deployment process. It assumes youre only deploying one VM in the deployment. After the VM has been deployed a subscription event triggers a workflow that adds the Disks through the vRA "Add Disk" resource action via the API.

You must have a vRA REST endpoint configured in vRO and store the rest endpoint (REST:RESTHost) and its username (string) and password(SecureString) in a configuration element. The code will handle subsiquent authentication to the vRA REST endpoint.

The cloud assembly blueprint must have an input named disks that uses the data grid element type that is passed to the vRO workflow as a custom property.

The Add VM Disks workflow iterates through the array of disks from the cloud assembly blueprint disks custom property and then calls the vRA Add Disk resource action for each disk.

