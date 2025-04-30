# Satellite Server Installation and Configuration Guide

## 1. Install RHEL 9

Set up a RHEL 9 system with the following hostname and network details. Also, make an entry in `/etc/hosts`:

- **Hostname**: `satellite.example.com`  
- **IP Address**: `192.168.0.10/24`

**Example entry for `/etc/hosts`:**
```bash
192.168.0.10 satellite.example.com
```

---

## 2. Install Satellite Server 6.16

Install Satellite Server 6.16 on the RHEL 9 system using the following details:

| Parameter                | Value                |
|--------------------------|----------------------|
| Organization Name        | pb10  |
| Location Name            | pb10      |
| Initial Admin Username   | admin      |
| Initial Admin Password   | redhat      |

---

## 3. Create and Download a Manifest

- Visit [access.redhat.com](https://access.redhat.com)
- Create a manifest and add the required subscriptions.

---

## 4. Import Manifest

- Import the downloaded manifest on the Satellite server.

---

## 5. Enable and Sync Repositories

Enable and sync the following repositories:

```bash
rhel-9-for-x86_64-baseos-rpms
rhel-9-for-x86_64-appstream-rpms
satellite-maintenance-6.16-for-rhel-9-x86_64-rpms
```

---

## 6. Create a Lifecycle Environment Path

Create the following lifecycle environment path:

```bash
Testing >> Development > Library
```

---

## 7. Create a Content View

Create a content view with the following details:

```bash
Content view name = RHEL9
Description       = RHEL9
Composite         = 9
Repositories      = rhel-9-for-x86_64-baseos-rpms, rhel-9-for-x86_64-appstream-rpms
```

---

## 8. Promote Content View

Promote the `RHEL9` content view to the `Testing` environment.

---

## 9. Create an Activation Key

Create an activation key with the following details:

```bash
Activation Key Name = RHEL9-key
Content View        = RHEL9
Lifecycle           = Testing
Release             = RHEL 9
```

---

## 10. Register a Host

Register a host with the Satellite server using the **global registration method** and the `RHEL9-key` activation key.
