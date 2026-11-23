# Multi-Tier Architecture: Two-Tier Deployment

## The Web/Application Tier
This tier, the Nextcloud `app` container, is the part end users interact with directly. It delivers the web interface and receives incoming HTTP requests on port 8080. It also handles file uploads, logins, and sharing actions, and passes anything that must be saved on to the database tier.

## The Database Tier
This tier, the `database` container running MariaDB, takes care of persistent data such as user accounts, login credentials, file metadata, and sharing permissions. It is never exposed directly to the public internet and only answers requests coming from the application tier.

## Why Separate Them?
Splitting the web and database layers into two containers lets each one be scaled, restarted, updated, or secured on its own. For example, updating the Nextcloud app does not require taking the database down, and the reverse is also true. It also shrinks the attack surface, because the database cannot be reached from the internet and is only accessible through the internal Docker network that the application tier uses.
