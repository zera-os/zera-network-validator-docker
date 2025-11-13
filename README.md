# zera-network-validator-docker-test

## Quick Start

### 1. Install Necessary Tools

```bash
sudo apt update
sudo apt install -y docker.io git
mkdir -p ~/.docker/cli-plugins/
curl -SL https://github.com/docker/compose/releases/download/v2.24.5/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose
chmod +x ~/.docker/cli-plugins/docker-compose
```

### 2. Clone The Repo

```bash
git clone https://github.com/zera-os/zera-network-validator-docker.git
cd zera-network-validator-docker
```

### 3. Make Scripts Executable

```bash
chmod +x ./scripts/setup.sh && chmod +x ./scripts/update-config.sh
```

### 4. Configure Your Validator

This project uses a `.env` file to generate your validator configuration.

#### 4.1: Copy the `.env` template

```bash
cp .env.example .env
```

#### 4.2: Edit .env with your validator details

```bash
nano .env
```

Update the values to match your server and wallet:

#### 4.3: Generate the config file

```bash
./scripts/setup.sh
```

This will create a complete Validator configuration file.

### 5. Start the Validator Node

Once your .env is configured and your validator.conf has been generated, you're ready to start your validator node.

```bash
docker compose up
```

If you've updated your .env or want to deregister from the network:

After changing your .env simply run:

```bash
./scripts/update-config.sh
docker compose up --force-recreate
```


## ⚙️ OS Compatibility Notes

### 🐧 Linux (Ubuntu/Debian)
All commands in this README are Linux-friendly out of the box.

### 🍎 macOS
- All bash scripts (`setup.sh`, `update-config.sh`) should work natively
- You must install Docker and Git via Homebrew or official downloads
- Use `chmod +x` only once if necessary

### 🪟 Windows
- Recommended: Use **WSL2 + Ubuntu** for easiest compatibility
- Alternatively, use Git Bash or PowerShell for basic script support
- If you use `cmd.exe`, bash scripts will not work without modifications
- Docker Desktop must be running with WSL2 backend


    
