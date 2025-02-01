# Jenkins Shared Library Demo - My Journey

This repository documents my journey in creating and implementing a Jenkins Shared Library. I started this project to streamline my CI/CD pipelines by extracting common build logic into a reusable library.

Basically, a Jenkins shared library is a function that references a particular groovy function for your pipeline (to avoid repeating code).

## Technologies I Used

Throughout this project, I worked with the following technologies:

*   **Jenkins** 
*   **Groovy**
*   **Docker**
*   **Git**
*   **Java**
*   **Maven**

## What I Accomplished

1. **Setting up Jenkins:** I started by spinning up a Jenkins server using Docker. 

![Jenkins](https://github.com/Princeton45/jenkins-shared-library/blob/main/images/new-jenkins.png)

2. **Crafted Reusable Functions:**  I delved into Groovy and developed a set of functions within the JSL. I created one function for building the JAR file and another for building the image.

`buildJar.groovy`
```groovy
#!/user/bin/env groovy

def call() {
    echo 'building the application...'
    sh 'mvn package'
}
```
`buildImage.groovy`
```groovy
#!/user/bin/env groovy

def call() {
    echo "building the docker image..."
    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
        sh 'docker build -t nanatwn/demo-app:jma-2.0 .'
        sh 'echo $PASS | docker login -u $USER --password-stdin'
        sh 'docker push nanatwn/demo-app:jma-2.0'
    }
}
```

3. **Integrated the Library into Jenkins:** I successfully integrated the JSL into my Jenkins instance, making it globally available for all pipelines.

![lib-global](https://github.com/Princeton45/jenkins-shared-library/blob/main/images/lib-global.png)

5. **Utilized the Library in a Pipeline:** Finally, I demonstrated the power of the JSL by using it within a sample Jenkinsfile. This showcased how easily I can now leverage pre-built functions in my pipelines.
