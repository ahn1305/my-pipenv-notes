<u>**Basic overview of pip and virtual env**</u> 

**pip** - for installing additional packages that doesn't come with standard python installation for using more functionalities.

**virtual environment** - way for us to have a specific environment for each project or application.

**Eg** - Each project will have it's own version of python and package

Using globally installed packages gets updated everytime when we update it, this may cause a problem with the code since it may accept only the older version of the package.

**pip** handles packages and **virtualenv** for handling the virtual environment, but using **pipenv** we can do both.

**<u>Installing pipenv</u>** 

```
pip install pipenv
```

 **<u>Using pipenv</u>**

```
pipenv install <package-name>
```

First it checks whether a virtualenv is created, if not creates one, gives location to pip file, then mentions the version of python, creates the env, and then shows the location, it's a regular env. creates **pipfile** and then install's the package

**Pipfile** - describes our env, similar to requirements.txt file

**Pipfile.lock** - should not touch that

**<u>Activating the virtualenvironment</u>** 

```
pipenv shell
```

**<u>Running a command inside the virtualenv</u>** 

```
pipenv run
```

<u>**Pipfile**</u>

Format used - **toml**

**Source** - from where we are downloading the packages

**Packages-section** - Contains the packages name installed, In this case

**requests = "*"** -> This means that we have not mentioned the version of requests module, so whenever we run pipenv install it updates to latest version automatically.

**Requires Section** - Contains the version of python

**<u>Pipfile.lock</u>** 

Generated file has details about the dependencies that our packages requires

**<u>Deactivating venv</u>**

```
exit
```

**<u>Running commands without activating the virtualenv</u>**

Let's say we want to run python within our current env

```
pipenv run <command> in this case python instead of command
```

**<u>Installing multiple packges</u>**

Create a requirements.txt file and use it from any location

```
pipenv install -r requirements.txt
```

**<u>Displaying the dependencies to add to requirements.txt file</u>**

```
pipenv lock -r
```

Lets say we want to have a package only in our development but not in production, so we can use the **--dev** option for this.

```
pipenv install <package-name> --dev
```

**<u>Uninstalling a package</u>**

```
pipenv uninstall <package-name>
```

**<u>Changing python version</u>**

Go to pipfile > change the version >  pipenv --python "version"

removes existing virtualenv, creates a new one with the required version

**<u>Recreating virtual env completely using pipfile</u>**

```
pipenv --rm and pipenv install
```

**<u>Checking for known security vulnerabilites of the installed packages</u>** 

```
pipenv check
```

**<u>List out the packages and it's dependencies</u>** 

```
pipenv check
```

**<u>Production tips</u>**

pipenv installs the latest version of the packages, pipfile.lock containes exact hashes and versions. To push the exact stuff, create or update the pipfile.lock with the current dependencies

```
pipenv lock 
```

```
pipenv install --ignore-pipfile
```

The above command creates env using pipfile.lock and ignores pipfile

**<u>Secret keys</u>** 

create a **.env** file, add required data.