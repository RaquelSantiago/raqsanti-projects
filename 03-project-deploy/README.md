# nuctl-deploy-checker-action

This action will attempt a model deployment using [`nuctl`](https://nuclio.io/docs/latest/tasks/deploying-functions/). This action will read `function.yaml` and `main.py` from root folder.

## Usage

```yml
- name: Nuctl Deploy Checker
  uses: Xu-Justin/nuctl-deploy-checker-action@v1
```

## Upcoming Features

- Custom `function.yaml` and `main.py` file name and path.

---

This project was developed as part of Nodeflux Internship x Kampus Merdeka.
