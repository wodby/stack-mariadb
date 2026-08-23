# MariaDB application stack for Kubernetes on Wodby

Deploy MariaDB applications on Kubernetes with Wodby.

This repository defines the Wodby stack manifests and default service
composition for MariaDB.

<!-- wodby:generated:start -->

## Stack contract

- [MariaDB stack on Wodby](https://wodby.com/stacks/mariadb)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definitions

- [MariaDB service](https://github.com/wodby/service-mariadb)
- [Adminer service](https://github.com/wodby/service-adminer)
- [phpMyAdmin service](https://github.com/wodby/service-phpmyadmin)

## What's included

| Component / service | Default configuration |
| --- | --- |
| MariaDB<br>`mariadb` | optional; enabled by default; volumes: `data` 20 GB |
| Adminer<br>`adminer` | optional; disabled by default; links: `db` → `mariadb` |
| phpMyAdmin<br>`phpmyadmin` | optional; disabled by default; links: `db` → `mariadb` |

Enabled optional services are selected by default but can be excluded when an
app is created. Disabled optional services are available but not selected by
default. Required services cannot be excluded.

## Validate the stack manifest

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

<!-- wodby:generated:end -->

## Deploy this stack

Add this stack from the Wodby catalog, then configure its enabled services and
integrations.

Review service versions, storage, links, and optional components when creating
the application. The same stack can be reused across development, staging, and
production environments.

## Maintain a custom version

1. Fork this repository.
2. Edit the stack manifest.
3. Import the repository as a [Git-backed stack](https://wodby.com/docs/2.0/stacks/create/#create-a-git-backed-stack).

When replacing or renaming a stack service, update every related link target
and derivative reference. Stack-local names and referenced service names are
distinct identifiers.
