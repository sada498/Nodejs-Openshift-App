## OpenShift Development Environment with GitHub and Visual Studio Code
1. To Access Openshit from command you need to install OpenShift command line interface (CLI). 
    Link https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/.
2. Download the openshift-client-<platform>-<version>.* .
3. Windows user need to add the path of the file to environment veriable
   To Help https://www.architectryan.com/2018/03/17/add-to-the-path-on-   windows-10/ 
4. Check the the version through command promit
      ``` 
       oc version
      ```
5. To login the Openshift account using API end point URL
     ```
      oc login <API END POINT Url>
      Username: <enter your user anem>
      Password: <enter your password>
     ```
6. Creating a new project 
     ```
      oc new-project <projectname>
      Ex: oc new-project node-test1
     ```
    ![Image of project](https://github.com/sada498/OpenShift-Apps/blob/master/node-express-hello/images/project%20create.gif)
    
7. Deploy the application 
     ```
      oc new-app -- name node-express-hello https://github.com/sada498/OpenShift-Apps.git#test-1  --context-dir node-express-       hello
     ```
 **Note: #test-1 is the branch of the GitHub repo to test application**
    
8. Open your web console and check the app deploy 
    In developer topology
9. Expose the application to public 
     ```
      oc expose svc/node-express-hello
     ```
10.  Go the web console check the application public end point

     ![Image of finall check](https://github.com/sada498/OpenShift-Apps/blob/master/node-express-hello/images/final%20check.gif)

## How to make CI/CD pipe line for GitHub and OpenShift 

1. Go to your GitHub project repo then settings 
2. Click on webhooks > add webhook 
3. To get the payload URL, switch to the OpenShift web console in your   browser, and then click on Builds in the navigation pane.
4. Click the your project build config to bring up the Build Config Overview page.
5. Scroll to the bottom of this page and locate the Copy URL with Secret link next to the GitHub type.
6. Click on the notepad icon to copy the payload URL.
     ![Image of webhook](https://github.com/sada498/OpenShift-Apps/blob/master/node-express-hello/images/Webhook.gif)
7. When you make changes or commits to github project.OpenShift make a automatic builds for the application.
