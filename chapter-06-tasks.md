# Manage users and Roles in Satellite

1. Create an organization with name `permissions`
2. Create a user `test` with password `redhat` in `permissions` org
3. test should should have `viewer` role
4. Create a user sam with password redhat in `permissions` org
5. sam user should have view hosts role assigned
6. Create a user bob with password redhat123 in `permissions` org
7. bob should should have org-admin role.
8. Create a user dean in `permissions` with password redhat
9. Dean should should be run remote execution jobs.
10. Create a user alice with password redhat `permissions`
11. alice user should have access to all remote execution features. It should be able to control all remote execution features and functionality.
