# Node.js with Cloudant app
description to follow


## Deployment steps (rough guide)
    
- Create a Code Engine project and switch to it.
- Configure a secret for the container registry, so that new images can be pushed there and pulled for deployment.
- Set up a build based on this repo and branch, the Dockerfile is in the root path
- Perform a buildrun
- Create an app **cfce-demo**, pick the image from the above build
- Bind the app **cf2ce-demo** to the Cloudant service instance with role **Manager**.
  ```sh
  ibmcloud ce app bind --name cf2ce-demo --si Cloudant-CFCE -r Manager
  ```
- Visit the app's URL.