# Jenkins

---

## 1.What is Jenkins

Jenkins is an open-source automation tool used in DevSecOps to help with continuous integration (CI) and continuous deployment (CD). In DevSecOps, Jenkins helps to add security checks into the software development pipeline, automating security tests and compliance checks throughout the development lifecycle. This helps to find and fix security issues early in the development process.CI/CD servers, including Jenkins, allow your team to set up the tests that you need to run. Jenkins helps structure the build cycle of a remote team.
It works with any programming language and for multiple platforms including Windows, Linux and macOS.

## 2. Main Features

- <mark>Build Automation:</mark> Jenkins compiles and builds your source code automatically, reducing human error and speeding up development.
- <mark>Automated Testing:</mark> It integrates with various testing frameworks to run tests automatically after each build.
- <mark>Continuous Deployment:</mark> Jenkins can automatically deploy your code to different environments after a successful build.
- <mark>Extensibility:</mark> Jenkins has over 1500 plugins that allow you to extend its functionalities to work with various tools and technologies in software development.

## 3.Architecture and Workflow

- <mark>Jenkins Server:</mark> The central system where CI/CD tasks are executed.
- <mark>Jenkins Nodes:</mark> Machines that run tasks as directed by the Jenkins server, distributing the workload.
- <mark>Pipelines:</mark> Written as code (in a Jenkinsfile), pipelines describe the steps in the CI/CD process, making it reproducible and version-controlled.

## 3.Benefits of Jenkins

- <mark>Automation:</mark> Reduces time and errors associated with manual processes.
- <mark>Fast Issue Detection:</mark> Frequent builds help quickly identify bugs, allowing for faster fixes.
- </mark>Flexibility:</mark> Works with many version control systems, programming languages, and testing frameworks.
- <mark>Active Community:</mark> A large number of users and developers contribute to improving the tool and its plugins continuously.
- <mark>plugins:</mark>a well-known tool with lots of community support, there are many plugins available (including well-known names like Slack, GitHub, Docker, Build Pipeline + more)

## 4.Typical Use Case

1. <mark>Code Commit:</mark> Developers push their code to a version control repository (like Git).
2. <mark>Automatic Build:</mark> Jenkins detects the change and triggers an automatic build.
3. <mark>Test Execution:</mark> Runs unit and integration tests.
4. <mark>Deployment:</mark> If tests pass, the code is deployed to a staging or production environment

## Link training in Jenkins on linkedin

https://www.linkedin.com/learning/l-essentiel-de-jenkins

Jenkins is a powerful tool for automating software development processes. It helps teams focus on writing quality code while reducing the time needed to deliver new features and bug fixes. When used properly, Jenkins makes CI/CD processes smoother and more reliable.

## 5.How to Install Jenkins in Ubuntu

![Alt text](media/Jenkins.png.png)

**_Attention_**
Make sure you choose a machine with at least 1GB of RAM. If you don’t have enough internal memory, Jenkins won’t run. For decent performance, 2 to 4GB is ideal.

### Step 1: Install Jenkins Using your Package Manager

On Ubuntu you can do this with:
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key |

sudo apt-key add

echo "deb http://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list

sudo apt-get update && sudo apt-get -y install Jenkins

**_Note:_** You have other installation options including two different release lines. See https://jenkins.io/download/ to learn the difference between weekly release and LTS (long-term support) options. Once installed, Jenkins will be running on port 8080. If you are accessing this server remotely, make sure to open the port 8080 in your firewall.

### Step 2: Open Your Browser

In your browser, go to http://your-ci-server-name.com:8080. If your machine is running Jenkins, the window should display the setup wizard.

### Step 3: Unlocking Jenkins

In order to ensure that you’re the real administrator of the machine, the password has been written to a specified log file. In a fresh terminal, type in sudo cat and then paste in the pathway provided on this page in order to get a temporary password. Then you can enter the password in the Administrator password field in your browser.

### Step 4: Customizing Jenkins Plugins

You can go ahead and click the Install the suggested plugins box. This will activate the download of a handful of useful plugins, including Git and some Pipeline plugins. You can always download other plugins as necessary to supplement these pre-selected options.

### Step 5: Create Admin Login

You can create your user account by adding a username, entering a new password, and including a full name and email address. Once you’re in Jenkins, you can choose to enable new users which will allow colleagues to create additional logins as needed.
