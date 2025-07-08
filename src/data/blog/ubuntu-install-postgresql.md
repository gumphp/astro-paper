---
author: chen
pubDatetime: 2025-07-08T15:50:00Z
modDatetime: 2025-07-08T15:50:00.934Z
title: ubuntu 安装 postgresql
slug: ubuntu-install-postgresql
featured: true
draft: false
tags:
  - ubuntu
  - postgresql
description:
  ubuntu 安装 postgresql
---

```bash
apt install -y postgresql-common
/usr/share/postgresql-common/pgdg/apt.postgresql.org.sh
```

```bash
# Import the repository signing key:
apt install curl ca-certificates
install -d /usr/share/postgresql-common/pgdg
curl -o /usr/share/postgresql-common/pgdg/apt.postgresql.org.asc --fail https://www.postgresql.org/media/keys/ACCC4CF8.asc
```

```bash file="/etc/apt/sources.list.d/pgdg.list"
# Create the repository configuration file:
. /etc/os-release
echo 'deb [signed-by=/usr/share/postgresql-common/pgdg/apt.postgresql.org.asc] https://apt.postgresql.org/pub/repos/apt $VERSION_CODENAME-pgdg main' > /etc/apt/sources.list.d/pgdg.list
```

```bash
# Update the package lists:
sudo apt update

# Install the latest version of PostgreSQL:
# If you want a specific version, use 'postgresql-17' or similar instead of 'postgresql'
sudo apt -y install postgresql
```

[官网链接](https://www.postgresql.org/download/linux/ubuntu/)