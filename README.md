# Setup pipeline using CircleCI, update GitHub Kubernetes manifest repo, and push image on Docker Hub

✨This repository contains the code of the Kubernetes manifest files.

## Architecture

![Architecture Diagram](https://cdn-images-1.medium.com/max/800/1*T5IRoSoiqT8qnYLUprsRUQ.png)

## Note and Links

This is the 3rd part of the project. Please go through the blog below to get more idea

Blog 1: [Blog 1] (https://medium.com/p/71983375e550/edit) 

Blog 2: [Blog 2] (https://medium.com/p/aa96d9a00391/edit) 

Blog 3: [Blog 3] (https://medium.com/p/e604412e959f/edit)

Blog 4: [Blog 4] (https://medium.com/p/9e3d62e1c093/edit)


## Synopsis
- When CircleCI notices any changes in the application code, it executes the jobs we have set up. There are a total of four jobs:

### Test: 
- This job tests the code. After the test job is completed, CircleCI proceeds to the next job. 
- Note: I didn't add this job to save time. 

### Build: 
- In the build job, CircleCI pulls the base Docker images and packages our application code inside the image.

### Push: 
- The push job pushes the newly generated images to Docker Hub with a new tag.

### Update Manifest: 
- After completing the push job, the last job is executed, which updates the Kubernetes manifest repository with the new tag. This enables ArgoCD to detect the change and apply it to the cluster.

Following this pipeline ensures that our application code is thoroughly tested, built into Docker images, and deployed with the updated manifest using the GitOps approach.

**This blog contains Three GitHub repositories**

➡️ [App Code] (https://github.com/chauhan-himani/AppCode)

➡️ [Terraform code] (https://github.com/chauhan-himani/kube_terraform)

➡️ [Manifest Repo] (https://github.com/chauhan-himani/kube_manifest)

If you want to learn how I created this project, please review my blogs. I've shared links to all the blogs above.👆

🙏 Thank you so much for reading.
