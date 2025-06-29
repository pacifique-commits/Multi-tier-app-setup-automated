# 🚀 Vprofile Automated Setup with Vagrant

This project provisions a **multi-tier Vprofile application** using **Vagrant** and **shell scripts** for automation. It sets up:

*  **MySQL** (db01)
*  **Memcached** (mc01)
*  **RabbitMQ** (rmq01)
*  **Tomcat** (app01)
*  **Nginx** (web01)

---

##  Prerequisites

Ensure you have the following installed:

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads)
* Git Bash or any Bash-compatible shell
* Vagrant Plugin:

  ```bash
  vagrant plugin install vagrant-hostmanager
  ```

---

## ⚡ Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/pacifique-commits/Multi-tier-app-setup-automated.git
   ```

2. **Navigate to the provisioning directory**

   ```bash
   cd vagrant/automated_provisioning
   ```

3. **Start the environment**

   ```bash
   vagrant up
   ```

This command will:

* Create **5 VMs** (`db01`, `mc01`, `rmq01`, `app01`, `web01`)
* Provision each component via shell scripts(	memcache.sh		rabbitmq.sh
application.properties	mysql.sh		tomcat.sh
backend.sh		nginx.sh		tomcat_ubuntu.sh)
* Automatically update `/etc/hosts` using `vagrant-hostmanager`

---

## 🛠 Services Overview

| Service   | Hostname | Port  |
| --------- | -------- | ----- |
| MySQL     | db01     | 3306  |
| Memcached | mc01     | 11211 |
| RabbitMQ  | rmq01    | 5672  |
| Tomcat    | app01    | 8080  |
| Nginx     | web01    | 80    |

---

## Access the Application

Once provisioning is complete, visit:
👉 `http://ipaddress of web01`

Ensure your local `/etc/hosts` file is properly updated by `vagrant-hostmanager`.

---

## 🧹 Teardown

To destroy all VMs:

```bash
vagrant destroy -f
```

---

## 📁 Directory Structure

```bash
automated_provisioning/
├── Vagrantfile
├── scripts/
│   ├── mysql.sh
│   ├── memcached.sh
│   ├── rabbitmq.sh
│   ├── tomcat.sh
│   └── nginx.sh
```

Each script provisions the respective service inside its VM.

---

## 🧾 Notes


* The **application WAR file** is built and deployed automatically via Maven in `tomcat.sh`.

---

## 🤝 Contributing

Feel free to fork the repo, make improvements, and submit a Pull Request (PR). Contributions are welcome!

