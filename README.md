## ansible - python venv

```bash
apt install ansible python3-venv virtualenv

export PYTHON=$(ansible --version | awk '/python version/ {print $NF}' | tr -d "\(\)")
$PYTHON -m venv ~/ansible-venv
source ~/ansible-venv/bin/activate
export PYTHONPATH=$(ls -1d ~/ansible-venv/lib/python*/site-packages)
cat << 'EOF' >> ~/.bashrc
if [ -z "$VIRTUAL_ENV" ]; then
  source ~/ansible-venv/bin/activate
fi
export PYTHONPATH=$(ls -1d ~/ansible-venv/lib/python*/site-packages)
EOF
```
