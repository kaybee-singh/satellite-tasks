# Satellite Chapter 2 – Practice Tasks

## Tasks

1. Verify that you are able to run hammer commands successfully, if not then login with admin user on hammer.  
2. Create a new organization named `finance` with hammer.  
3. Create a new location `berlin` with hammer.  
4. Create a new manifest for Satellite on access.redhat.com and add some subscriptions.  
5. Export the manifest and save it.  
6. Import the manifest to Satellite with hammer in `finance` Organization.  
7. Set default organization for hammer to `finance`.  
8. Set default location for hammer to `berlin`.  
9. Enable and sync below repositories with hammer in finance organization.

    **Note:** As we have set the default organization for hammer so there is no need to manually provide the organization name/id with hammer command.  
    ```
    Red Hat Enterprise Linux 9 x86_64 - AppStream (RPMs)
    Red Hat Enterprise Linux 9 x86_64 - BaseOS (RPMs)
    Red Hat Enterprise Linux 9 Satellite Tools 6.16 RPMs
    ```

10. Create a new lifecycle named `stable` with hammer.  
11. Create a new content view with hammer with below details and then publish a new version.
    ```
    Content view name = finance_rhel9
    Description       = finance_rhel9
    Composite         = no
    Repositories      = rhel-9-for-x86_64-baseos-rpms, rhel-9-for-x86_64-appstream-rpms
    ```
12. Promote the content view to `stable` life cycle.  
13. Create an activation key with hammer with below details.
    ```
    Activation Key Name = finance_rhel9_key
    Content View        = finance_rhel9
    Lifecycle           = stable
    Release             = RHEL 9
    ```
14. Set log levels to `DEBUG` for all components of Satellite with hammer.  
15. Set log levels to `PRODUCTION` for all components of Satellite with hammer.
16. Register a host in `finance` organization and use `finance_rhel9_key` activation key.
