**Role-based access control (RBAC)** is an [[Authentication vs Authorization|authorization]] strategy that refers to the idea of assigning permissions to users based on their role within an organization. It offers a simple, manageable approach to access management that is less prone to error than assigning permissions to users individually.

When using RBAC for Role Management, you analyze the needs of your users and group them into roles based on common responsibilities. You then assign one or more roles to each user and one or more permissions to each role. The user-role and role-permissions relationships make it simple to perform user assignments since users no longer need to be managed individually, but instead have privileges that conform to the permissions assigned to their role(s).

RBAC is an additive model, so if you have overlapping role assignments, your effective permissions are the union of your role assignments.

When planning your access control strategy, it’s best practice to assign users the fewest number of permissions that allow them to get their work done.

## Benefits of RBAC

With RBAC, access management is easier as long as you adhere strictly to the role requirements. 
RBAC helps you:

- create systematic, repeatable assignment of permissions
- easily audit user privileges and correct identified issues
- quickly add and change roles, as well as implement them across APIs
- cut down on the potential for error when assigning user permissions
- integrate third-party users by giving them pre-defined roles
- more effectively comply with regulatory and statutory requirements for confidentiality and privacy
### References
https://auth0.com/docs/manage-users/access-control/rbac