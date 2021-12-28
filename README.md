# Optuna dashboard systemd

* Install optuna dashboard as systemd daemon. 
* Run daemon with your regular user.

# Requirements

* Linux
* miniconda
* mariadb/mysql

# Setup database

```bash
$ mysql -u root -e "CREATE DATABASE IF NOT EXISTS example"
```

# Setup optuna dashboard

**Step 1**: Clone repo. 

```bash
$ cd ~
$ git clone https://github.com/adrianmarino/optuna-dashboard.git
$ cd optuna-dashboard
```

**Step 2**: Create conda environment required to run optuna dashboard.

```bash
$ conda env update -f environment.yml
```

**Step 3**: Copy service file user level systemd config path:

```bash
$ cp optuna-dashboard.service ~/.config/systemd/user/
```

**Step 4**: Refresh systemd daemon with updated config.

```bash
$ systemctl --user daemon-reload
```

**Step 5**: Start service on boot.

```bash
$ systemctl --user enable optuna-dashboard
```

**Step 6**: Start optuna dashbord as systemd daemon.

```bash
$ systemctl --user start optuna-dashboard
```

# Config file

`config.conf`:
```bash
CONDA_PATH="/opt/miniconda3"
ENV="optuna-dashboard"
DB_URL="mysql://root:1234@localhost/example"
PORT="9090"
HOST="192.168.1.10"
```
