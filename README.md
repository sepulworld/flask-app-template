# flask-app-template

Flask app template with User auth and local development prepped up

## Requirements for local usage

* python3
* poetry 
* pygit2 (after libssh2, libgit2 installed)

## Install Python Poetry
```
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
```

## Setup (Needs specific git libs)
```
pip uninstall pygit2
xcode-select --install
brew install libssh2 libgit2
pip install pygit2 --no-binary pygit2
poetry install
```

#### Create Python Flask app via Battenberg

```
# replace "myapp" with your app name
battenberg -O myapp install --initial-branch master git@github.com:sepulworld/flask-app-template.git 
app [app]: myapp 
```

Will generate git repo and init
```
myapp/
├── .cookiecutter.json
├── .github
│   └── workflow
  │   └── lint.yml
├── .gitignore
├── .git
├── README.md
└── app 
```

#### Create Github Repo 

Create a Github public or private repo your new project 

#### Push initial commit to trigger cluster setup
```
# example init and push, please replace CLUSTER_NAME_HERE with eks cluster name
cd myapp 
git remote add origin git@github.com:<user>/myapp.git
git push -u origin main
```

#### Battenbug Upgrades to your app

If you want to sync new changes from flask-app-template to your app
 
```
cd myapp 
git branch template main 
git checkout -b template_sync
battenberg upgrade
```

#### What is Battenberg?

https://github.com/zillow/battenberg#battenberg


