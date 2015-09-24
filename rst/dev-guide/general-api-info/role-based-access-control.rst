.. _role-based-access-control

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
`RBAC <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/Role_Based_Access_Control-d1e808.html>`__
section in the "Cloud Identity Client Developer Guide". For information
about how to perform the following tasks, see the "Cloud Identity Client
Developer Guide":

-  `Create account
   users <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/POST_addUser__v2.0_users_User_Calls.html>`__

-  `Assign roles to account
   users <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/PUT_addUserRole__v2.0_users__userId__roles_OS-KSADM__roleid__Role_Calls.html>`__

-  `Delete roles from account
   users <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/DELETE_deleteUserRole__v2.0_users__userId__roles_OS-KSADM__roleid__Role_Calls.html>`__

..  note::
    The account owner (identity:user-admin) role cannot hold any additional
    roles because it already has full access to all capabilities.
