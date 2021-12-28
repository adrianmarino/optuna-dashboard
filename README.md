# Optuna dashboard setup

Install optuna dashboard as systemd daemon under linux. This run with your regular linux user.

# Requirements

* miniconda
* mariadb/mysql

# Setup database

```bash
$ mysql -u root -e "CREATE DATABASE IF NOT EXISTS example"
```

# Setup Optuna dashboard

**Step 1**: Clone repo. 

```bash
git clone https://github.com/adrianmarino/optuna-dashboard.git
cd optuna-dashboard
```

**Step 2**: Create conda environment required to run optuna dashboard.

```bash
conda env update -f environment.yml
```

**Step 3**: Copy service file user level systemd config path:

```bash
cp optuna-dashboard.service ~/.config/systemd/user/
```

**Step 4**: Refresh systemd daemon with updated config.

```bash
systemctl --user daemon-reload
```

**Step 5**: Start service on boot.

```bash
systemctl --user enable optuna-dashboard
```

**Step 6**: Start optuna dashbord as systemd daemon.

```bash
systemctl --user start optuna-dashboard
```
