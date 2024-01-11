# ansible_role_ensure_gitea_state

[![Validate infrastructure as code](https://github.com/garliclabs/ansible_role_ensure_gitea_state/actions/workflows/validation.yml/badge.svg)](https://github.com/garliclabs/ansible_role_ensure_gitea_state/actions/workflows/validation.yml)

Manage the state and configuration of a gitea deployment in your kubernetes cluster via helm.  

## Requirements

Kubernetes, Helm

## Role Variables

**gitea_kubeconfig:** Path to the kubeconfig for your kubernetes cluster  
**gitea_namespace:** Kubernetes namespace to deploy gitea in  
**gitea_chart_version:** Version of gitea helm chart see: [bitnami gitea](https://artifacthub.io/packages/helm/bitnami/gitea)  
**gitea_name:** Name of your gitea!  
**gitea_state:** State of the deployment, can be either present or absent  
**gitea_value_path:** Path to your helm values file, if not set a minimal default values will be set except of the gitea name  

## Development

### Testing

* Create venv: `python3 -m venv ./venv`
* Install pip requirements: `venv/bin/pip install -r pip_requirements.txt`
* Execute tests `venv/bin/molecule test`

### Linting & static security analyser

Both the linter and the static security analyser are running on each push on the github actions pipeline.  

* As linter [ansible-lint](https://ansible.readthedocs.io/projects/lint/) is used. For installation documentation see [ansible lint installing](https://ansible.readthedocs.io/projects/lint/)
  * Just run `ansible-lint`

* To check if there are any passwords, tokens... hardcoded, [kics](https://kics.io/index.html) is used to ensure a secure IaC repository.  
  * Run it locally `docker run -t -v $PWD:/path checkmarx/kics:latest scan -p /path -o "/path/"`

## License

GNU General Public License version 3
