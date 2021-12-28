# Optuna dashboard setup


# Setup

**Step 1:**

```bash
git clone ..
cd optuna-dashboard
```

```bash
cp optuna-dashboard.service ~/.config/systemd/user/
```

```bash
systemctl --user daemon-reload

```
```bash
systemctl --user enable optuna-dashboard
```

```bash
systemctl --user start optuna-dashboard
```
