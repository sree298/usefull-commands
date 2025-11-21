# 🚀 Jenkins Main Commands Cheat Sheet

## 🖥 Jenkins Service Commands (Linux)

| Command | Description |
|--------|-------------|
| `systemctl start jenkins` | Start Jenkins service |
| `systemctl stop jenkins` | Stop Jenkins service |
| `systemctl restart jenkins` | Restart Jenkins service |
| `systemctl status jenkins` | Check Jenkins status |
| `journalctl -u jenkins -f` | View Jenkins live logs |
| `journalctl -u jenkins --since "10 min ago"` | View logs for last 10 min |

---

## 🔐 Initial Setup & Password

| Command | Description |
|--------|------------|
| `cat /var/lib/jenkins/secrets/initialAdminPassword` | View initial admin password |
| `sudo cat /var/log/jenkins/jenkins.log` | Jenkins startup log file |

---

## 📦 Install & Update Jenkins

| Command | Description |
|--------|------------|
| `sudo yum install jenkins` | Install Jenkins (RHEL/Amazon Linux/CentOS) |
| `sudo apt install jenkins` | Install Jenkins (Ubuntu/Debian) |
| `sudo yum update jenkins` | Update Jenkins |
| `sudo apt upgrade jenkins` | Upgrade Jenkins |

---

## 📂 Jenkins Folder Paths

| Purpose | Path |
|---------|------|
| Jenkins Home | `/var/lib/jenkins/` |
| Configuration files | `/etc/sysconfig/jenkins` / `/etc/default/jenkins` |
| Log files | `/var/log/jenkins/jenkins.log` |
| Jobs directory | `/var/lib/jenkins/jobs/` |
| Plugins directory | `/var/lib/jenkins/plugins/` |

---

## 🧰 Jenkins CLI Commands

| Command | Description |
|--------|-------------|
| `java -jar jenkins-cli.jar -s http://localhost:8080/ help` | List CLI commands |
| `java -jar jenkins-cli.jar -s http://localhost:8080/ list-jobs` | List jobs |
| `java -jar jenkins-cli.jar -s http://localhost:8080/ build <job-name>` | Trigger job build |
| `java -jar jenkins-cli.jar -s http://localhost:8080/ build <job> -p key=value` | Build with parameters |
| `java -jar jenkins-cli.jar -s http://localhost:8080/ delete-job <job-name>` | Delete job |
| `java -jar jenkins-cli.jar -s http://localhost:8080/ install-plugin <plugin-name>` | Install plugin |
| `java -jar jenkins-cli.jar -s http://localhost:8080/ restart` | Restart Jenkins |

---

## 🌐 Jenkins URL & Ports

| Description | Command |
|------------|---------|
| Default Jenkins URL | `http://localhost:8080` |
| Set custom port | Change in `/etc/default/jenkins` or `/etc/sysconfig/jenkins` |

---

## 🚧 Pipeline (Declarative Example)

```groovy
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo "Building..."
      }
    }
    stage('Test') {
      steps {
        echo "Testing..."
      }
    }
    stage('Deploy') {
      steps {
        echo "Deploying..."
      }
    }
  }
}
