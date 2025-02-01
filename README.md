# Jenkins Shared Library Demo - My Journey

This repository documents my journey in creating and implementing a Jenkins Shared Library. I embarked on this project to streamline my CI/CD pipelines by extracting common build logic into a reusable library.

## What I Accomplished

1. **Set up the Foundation:** I started by spinning up a Jenkins server using Docker. This provided me with a clean and isolated environment to work with.
    *   **Possible Picture:** Screenshot of the running Jenkins container in Docker Desktop or a similar tool.
2. **Created the Shared Library Repository:** I initialized a separate Git repository specifically for my Jenkins Shared Library (JSL) project. This ensures version control and collaboration.
    *   **Possible Picture:** Screenshot of the repository structure on GitHub, GitLab, or a similar platform.
3. **Crafted Reusable Functions:**  I delved into Groovy and developed a set of functions within the JSL. These functions encapsulate common build tasks like compiling Java code with Maven, building docker images, running unit tests, etc., making them readily available for any pipeline.
    *   **Possible Picture:** Snippet of a Groovy function from the `vars` directory, highlighting its purpose.
4. **Integrated the Library into Jenkins:** I successfully integrated the JSL into my Jenkins instance, making it globally available for all pipelines.
    *   **Possible Picture:** Screenshot of the Jenkins Global Pipeline Libraries configuration page showing my library.
5. **Utilized the Library in a Pipeline:** Finally, I demonstrated the power of the JSL by using it within a sample Jenkinsfile. This showcased how easily I can now leverage pre-built functions in my pipelines.
    *   **Possible Picture:** Screenshot of a Jenkins pipeline run successfully executing a stage that uses a function from the shared library.
    *   **Possible Picture:** Screenshot of the Jenkinsfile, showing how the shared library is imported and its functions are called.

## Technologies I Employed

Throughout this project, I worked with the following technologies:

*   **Jenkins:**  The core CI/CD tool that orchestrates the pipelines.
*   **Groovy:** The scripting language used to build the shared library functions.
*   **Docker:** Used to containerize and run Jenkins for a consistent environment.
*   **Git:** For version control of both the shared library and the example project.
*   **Java:** The sample application being built is based on Java.
*   **Maven:** To manage dependencies and the build process of the Java project.

## Conclusion

This project was a valuable learning experience. I now have a functional Jenkins Shared Library that I can use to simplify and standardize my CI/CD pipelines. I'm excited to continue expanding this library with more reusable functions and further optimize my development workflow.