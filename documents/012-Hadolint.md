# Hadolint

---

## 1. what is hadolint

Hadolint is a Dockerfile linter that checks Dockerfiles against a set of guidelines for best practices and potential issues. It helps maintain consistency, security, and efficiency in Docker image files.

## 2. How to use with docker

```bash
docker run --rm -i hadolint/hadolint < Dockerfile
```

## 3. Installation on Ubuntu

```bash
sudo apt update
sudo apt install hadolint
```

## 4. Basic Command

```bash
hadolint /path/to/your/Dockerfile
```

## 5. Ignoring Errors

- Ignoring Errors: Hadolint allows you to ignore specific linting rules using comments within your Dockerfile:

```dockerfile

# hadolint ignore=DL3000

FROM ubuntu:latest
...
```

- Here, DL3000 is an example of a rule ID that you want Hadolint to ignore for this specific line.
