.. _role-based-access-control:

Role Based Access Control
~~~~~~~~~~~~~~~~~~~~~~~~~~

Role Based Access Control (RBAC) restricts access to the capabilities of
Rackspace Cloud services, including the RackConnect API, to authorized
users only. RBAC enables Rackspace Cloud customers to specify which
account users of their Cloud account have access to which RackConnect
API service capabilities, based on roles defined by Rackspace.

The permissions to perform certain operations in the RackConnect API –
create, read, update, delete – are assigned to specific roles. The Cloud
account owner (identity:user-admin) can create account users on the
account and then assign roles, either global (multiproduct) or
product-specific, to those users. Each account has only one account
owner, and that role is assigned by default to any Rackspace Cloud
account when the account is created.

For more information about RBAC, see the 
:rax-devdocs:`RBAC<cloud-identity/v2/developer-guide/#document-authentication-info/role-based-access-control>` 
section in the "Cloud Identity Client Developer Guide". See the following links for information 
about how to manage users and roles by using the Cloud Identity service:

-  :rax-devdocs:`Add account user<cloud-identity/v2/developer-guide/#add-user>`   

-  :rax-devdocs:`Assign roles to account users<cloud-identity/v2/developer-guide/#add-role-to-user>`

-  :rax-devdocs:`Delete roles from account users<cloud-identity/v2/developer-guide/#delete-global-role-from-user>`

..  note::
    The account owner (identity:user-admin) role cannot hold any additional
    roles because it already has full access to all capabilities.
