# Dockle

---

## 1. What is Dockle

Dockle is a powerful container image linter crafted to elevate the security and adherence to best practices of Docker images.

## 2. Key Features

- **Security Assessment:**

  - Dockle analyzes container images for security.
  - Identifies potential vulnerabilities and insecure configurations.

- **Best-Practice Compliance:**

  - Checks Docker images against industry standards.
  - Ensures images follow recommended guidelines for configuration and image layering.

- **Ease of Use:**

  - Integrates seamlessly into workflows.
  - User-friendly command-line interface for easy image linting.

- **Practical Recommendations:**
  - Provides actionable suggestions to improve image security and configuration.

## 3. Checkpoint Summary

- Details of each checkpoint: see [CHECKPOINT.md](https://github.com/goodwithtech/dockle/blob/master/CHECKPOINT.md)
- CIS's Docker Image Checkpoints:

  | CODE        | DESCRIPTION                            | LEVEL |
  | ----------- | -------------------------------------- | ----- |
  | CIS-DI-0001 | Create a user for the container        | WARN  |
  | CIS-DI-0002 | Use trusted base images for containers | FATAL |
  | CIS-DI-0003 | Do not install unnecessary packages    | FATAL |
  | ...         | ...                                    | ...   |

- Dockle Checkpoints for Docker:

  | CODE        | DESCRIPTION                        | LEVEL |
  | ----------- | ---------------------------------- | ----- |
  | DKL-DI-0001 | Avoid sudo command                 | FATAL |
  | DKL-DI-0002 | Avoid sensitive directory mounting | FATAL |
  | DKL-DI-0003 | Avoid apt-get dist-upgrade         | WARN  |
  | ...         | ...                                | ...   |

- Dockle Checkpoints for Linux:

  | CODE        | DESCRIPTION              | LEVEL |
  | ----------- | ------------------------ | ----- |
  | DKL-LI-0001 | Avoid empty password     | FATAL |
  | DKL-LI-0002 | Be unique UID/GROUPs     | FATAL |
  | DKL-LI-0003 | Only put necessary files | INFO  |

**Level Definitions:**

Dockle has 5 check levels.

| LEVEL | DESCRIPTION                                                          |
| ----- | -------------------------------------------------------------------- |
| FATAL | Be practical and prudent                                             |
| WARN  | Be practical and prudent, but limited uses (even if official images) |
| INFO  | May negatively inhibit the utility or performance                    |
| SKIP  | Not found target files                                               |
| PASS  | Not found any problems                                               |

## 4. Dockle Installation

- **Retrieve the Latest Version from GitHub Releases:**

  ```bash
  VERSION=$(
    curl --silent "https://api.github.com/repos/goodwithtech/dockle/releases/latest" | \
    grep '"tag_name":' | \
    sed -E 's/.*"v([^"]+)".*/\1/' \
  )
  ```

- **Download the Dockle Debian Package:**

  ```bash
  curl -L -o dockle.deb https://github.com/goodwithtech/dockle/releases/download/v${VERSION}/dockle_${VERSION}_Linux-64bit.deb
  ```

- **Install the Dockle Debian Package:**

  ```bash
  sudo dpkg -i dockle.deb && rm dockle.deb
  ```

## 5. Basic Dockle Scan

### 5.1. Run Dockle to scan the Docker image

```bash
dockle IMAGE_NAME
```

### 5.2. Dockle Scan with JSON Output

```bash
dockle -f json -o results.json IMAGE_NAME
```

### 5.3. Set Non-Zero Exit Code on Warnings or Errors

```bash
dockle --exit-code 1 [IMAGE_NAME]
```

- By default, Dockle exits with code 0 even if there are problems. This command uses the `--exit-code` option to exit with a non-zero exit code if WARN or FATAL alerts are found during the scan.

### 5.4. Specify Specific Checks to Ignore

```bash
dockle -i CIS-DI-0001 -i DKL-DI-0006 IMAGE_NAME
```

## 6. Docker Hub Authentication

```bash
export DOCKLE_AUTH_URL=https://registry.hub.docker.com
export DOCKLE_USERNAME={DOCKERHUB_USERNAME}
export DOCKLE_PASSWORD={DOCKERHUB_PASSWORD}
```
