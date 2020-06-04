# AutoConnect-ASCSubscriptions
author: Lior Tamir

The playbook is triggered on a scheduled basis.
It is running on behalf of a registered Azure AD application, which monitors a certain management group.
For each subscription this app has access to, if the subscription doesn't have an Azure Security Center connection enabled, a connection to Azure Sentinel is created.

The registered application needs to have the following RBAC Roles:

1. Security Reader Role on the Management Group which ASC subscriptions are under.
This is required for listing all available subscriptions, including new ones which are not connected yet. In some organizations, it is the Root Management Group.

2. Azure Sentinel Contributor Role on the Azure Sentinel workspace.
This is required for checking if a connection exists for a certain subscription, and for creating the connection rule from a not connected subscription to Azure Sentinel.

Documentation references:

<li>Azure Management groups as containers of subscriptions to monitor
<ul>
<li><a href="https://docs.microsoft.com/en-us/azure/governance/management-groups/overview" target="_blank" rel="noopener">Learn more about Azure Management Groups</a></li>
</ul>
</li>
<li>Azure Active Directory registered application, assigned with RBAC roles
<ul>
<li><a href="https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals" target="_blank" rel="noopener">Learn more about applications in Azure Active Directory.</a></li>
</ul>
</li>
</ul>

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FAzure-Sentinel%2Fmaster%2FPlaybooks%2FAutoConnect-ASCSubscriptions%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton""/>
</a>
<a href="https://portal.azure.us/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FAzure-Sentinel%2Fmaster%2FPlaybooks%2FAutoConnect-ASCSubscriptions%2Fazuredeploy.json" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"/>
</a>