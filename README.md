# Optuna dashboard setup

Install optuna dashboard as systemd daemon under linux. This run with your regular linux user.

# Requirements

* miniconda

# Setup

**Step 1**: Clone repo. 

```bash
git clone https://github.com/adrianmarino/optuna-dashboard.git
cd optuna-dashboard
```

**Step 2**: Create conda environment required to run optuna dashboard.

```bash
conda env update -f environment.yml
```

**Step 2**: Copy service file user level systemd config path:

```bash
cp optuna-dashboard.service ~/.config/systemd/user/
```

**Step 3**: Refresh systemd daemon with updated config.

```bash
systemctl --user daemon-reload
```

**Step 4**: Start service on boot.

```bash
systemctl --user enable optuna-dashboard
```

**Step 5**: Start optuna dashbord as systemd daemon.

```bash
systemctl --user start optuna-dashboard
```
