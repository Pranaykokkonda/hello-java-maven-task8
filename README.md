# 🚀 Hello Java Maven + Jenkins CI 🛠️☕

A simple **"Hello World"** Java project built using **Maven** and **Jenkins**, demonstrating Continuous Integration with a working Java console output.

---

## 📦 What It Does

- Compiles a basic Java app using Maven
- Prints: `Hello, Jenkins + Maven!`
- Uses a **Jenkins Freestyle job** to build and run the app
- Java 17 compatible

---
## 🧰 Jenkins Setup Instructions ⚙️🖥️
- Download and install Jenkins from the official Jenkins website by clicking the "Install Jenkins" button below.

<a href="https://www.jenkins.io/doc/book/installing/linux/" target="_blank">
  <img src="https://img.shields.io/badge/Install%20Jenkins-007BFF?style=for-the-badge&logo=githubpages&logoColor=white" alt="Install Jenkins Badge" />
</a>

-  After successful installation verify the actual JDK path by following command
  
```bash
readlink -f $(which java)
```

```bash
ls /usr/lib/jvm/
```
![image alt](https://github.com/Pranaykokkonda/hello-java-maven-task8/blob/bc7a24ad6422b79324ffef533975554fc7fcb943/01-actual-JDK-path.jpg)
-  Copy the path.

---
## ☕🔧 Java and Maven Setup 🏗️📦
### 1. ☕ Java Setup in Jenkins
Go to: Manage Jenkins → Tools (Global Tool Configuration)
- **Under JDK:** Uncheck **Install automatically**
- **Name:** java
- **JAVA_HOME:** <Paste the path here>  (In my-case its **/usr/lib/jvm/java-17-openjdk-amd64**)

### 2. 🏗️ Maven Setup ⚙️📦
In same section, under Maven:

**Name:** maven

**Choose maven version** (e.g., Maven 3.8.6)

---
## 🚀 Jenkins Job Configuration

- Go to Jenkins Dashboard → **New Item**

Choose **Freestyle project**, name it: Hello-Maven-Build

- **In Build Environment:**

(Optional) Check “Delete workspace before build starts”

- **In Build Steps:**

Step 1: Add Invoke top-level Maven targets

Goals: clean package

Step 2: Add Execute shell

**Command:**

```bash
java -cp target/classes HelloWorld
```
- **Save the job**

- **Click Build Now**

- Click the build number → **Console Output**

---
## 🖥 Expected Console Output 🖨️🔍
  
[INFO] BUILD SUCCESS

Hello, Jenkins + Maven!

---
## 📤 Output 🖨️🔍
-  **Pipeline Build**
  
![image alt](https://github.com/Pranaykokkonda/hello-java-maven-task8/blob/bc7a24ad6422b79324ffef533975554fc7fcb943/02-pipeline-build.jpg)
-  **Info - Build Success**
  
![image alt](https://github.com/Pranaykokkonda/hello-java-maven-task8/blob/bc7a24ad6422b79324ffef533975554fc7fcb943/03-info-build-success.jpg)
-  **Info - Build Success with output**

![image alt](https://github.com/Pranaykokkonda/hello-java-maven-task8/blob/bc7a24ad6422b79324ffef533975554fc7fcb943/04-info-bs-with-output.jpg)

---
