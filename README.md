# Intro
This role installs and configures a Dockerized Home-Assistant application.

## Requirements
While there's no explicit dependency roles, the target machine should be able to act as a Docker host.  The `geerlingguy.docker` Ansible role is a suitable solution.

## Role Variables
See the [comment in the default variables file](defaults/main.yml) for information on configuration.

## Dependencies
None.

## Example Playbook
    - hosts: whatever
      roles:
        - triplepoint.home_assistant

## Role Testing
This role is tested with `molecule`, using `pipenv` to handle dependencies and the Python testing environment.

### Setting Up Your Execution Environment
``` sh
pip install pipenv
```

Once you have `pipenv` installed, you can build the execution virtualenv with:
``` sh
pipenv install --dev
```

### Running Tests
Once you have your environment configured, you can execute `molecule` with:
``` sh
pipenv run molecule test
```

### Regenerating the Lock File
You shouldn't have to do this very often, but if you change the Python package requirements using `pipenv install {some_package}` commands or by editing the `Pipfile` directly, or if you find the build dependencies have fallen out of date, you might need to regenerate the `Pipfile.lock`.
``` sh
pipenv update --dev
```
Be sure and check in the regenerated `Pipfile.lock` when this process is complete.

## License
MIT
