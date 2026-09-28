# GitHub Actions Self-Hosted Runner Setup on `mlthrive` and `healthview`

This guide describes how to install and configure a GitHub Actions self-hosted runner on a Debian-based system. The runner will be installed in `/opt/github-runner` under a dedicated system user, and set up as a systemd service.

---

## 🧑‍💻 Create the `github-runner` User

Create a system user without a home directory, using `/opt/github-runner` as the base directory:

```bash
sudo useradd --system --shell /bin/bash --home-dir /opt/github-runner github-runner
````

Add the `github-runner` user to the `docker` group (if your jobs require Docker access):

```bash
sudo usermod -aG docker github-runner
```

---

## 📁 Create the Runner Directory

Create and assign permissions for the runner directory:

```bash
sudo mkdir -p /opt/github-runner
sudo chown github-runner:github-runner /opt/github-runner
```

---

## 🔁 Switch to the `github-runner` User

```bash
sudo su - github-runner
```

---

## 📦 Download and Extract the GitHub Runner

Download the runner binary (version 2.326.0 in this example):

```bash
curl -o actions-runner-linux-x64-2.326.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.326.0/actions-runner-linux-x64-2.326.0.tar.gz
```

(Optional) Verify the SHA256 checksum:

```bash
echo "9c74af9b4352bbc99aecc7353b47bcdfcd1b2a0f6d15af54a99f54a0c14a1de8  actions-runner-linux-x64-2.326.0.tar.gz" | shasum -a 256 -c
```

Extract the archive:

```bash
tar xzf ./actions-runner-linux-x64-2.326.0.tar.gz
```

---

## ⚙️ Configure the Runner

Configure the runner with your repository URL and registration token:

```bash
./config.sh --url https://github.com/curatimeXai --token YOUR_GITHUB_TOKEN
```

---

## ▶️ Start the Runner Manually (Optional)

You can start the runner manually to test it:

```bash
./run.sh
```

Then exit back to the main user:

```bash
exit
```

---

## 🛠️ Set Up the Runner as a `systemd` Service

Install the service:

```bash
sudo ./svc.sh install github-runner
```

Start the service:

```bash
sudo ./svc.sh start github-runner
```

---

## 🧪 Check Runner Status

To verify that the runner is running:

```bash
sudo ./svc.sh status
```

Or:

```bash
systemctl is-active actions.runner.*
```

---

## ✅ Done!

The runner is now installed and running as a system service under the `github-runner` user in `/opt/github-runner`.

Make sure to monitor it in your GitHub repository under **Settings → Actions → Runners**.

---
