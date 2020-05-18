install ansible
```
sudo apt install python3-venv
python3 -m venv .venv
source .venv/bin/activate
pip3 install ansible
ansible --version
```

hash password for postgre
```
echo "md5$(echo -n 'x1)fJJis11' | md5sum | awk '{print $1}')"
```
