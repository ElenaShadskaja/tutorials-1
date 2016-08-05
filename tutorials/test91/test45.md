---
title: 12Developing and deploying a basic Java application on SAP HANA Cloud Platform
description: Develop and deploy your first Java application using the SAP HANA Cloud Platform Tools for Java
tags: [  tutorial>beginner, topic>cloud, topic>java, products>sap-hana-cloud-platform ]
---

 
## Next Steps
 - http://go.sap.com/developer/tutorial-navigator.html, http://go.sap.com/developer/tutorials.html

## Details
### You will learn  
In this tutorial you will create a Dynamic Web project, a servlet to respond to a browser request and after running it in your local development environment, deploy it to SAP HANA Cloud Platform.



---


1. The first step in building your application is to create a new Dynamic Web Project. Open your Eclipse IDE with the installed SAP HANA Cloud Platform Tools. Make sure the **Java EE perspective** is open by choosing **Window > Open Perspective > Other**.

    ![open other perspective](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

2. Then choose the perspective **Java EE (Default)** and confirm by clicking **OK**.

    ![open J2EE perspective](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

3. The J2EE perspective is now open.1

    ![J2EE perspective is open](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

4. In the Eclipse main menu choose **File > New > Dynamic Web Project** to open the respective wizard.

    ![open wizard](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)
    
5. In the **New Dynamic Web Project Wizard** define the **Project name** to be `helloworld`. Make sure the **Target Runtime** is set to `Java Web` the Server Runtime Environment that has been created in the tutorial [Configuring Eclipse with SAP HANA Cloud Platform Tools for Java](http://go.sap.com/developer/tutorials/hcp-java-eclipse-setup.html). Leave all other settings untouched and click **Finish** to create the project.

    ![project wizard](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

    The `helloworld` project is now ready for your code.
    
    ![hello world project](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

6. In Java EE, web applications are implemented as `Servlets`. On the newly created `helloworld` project node, open the context menu with a right-click and choose **New > Servlet** to open the Create Servlet wizard.

    ![open servlet wizard](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg) 


7. In the Create Servlet wizard enter `helloworld` as Java package and `HelloWorldServlet` as Class name. This will create Java classes with the respective package and name. Choose **Next**.

    ![create servlet wizard](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg) 

8. You will want this Servlet to be accessible via the URL `<servername>/helloworld`, for example `http://localhost:8080/helloworld`. For this we will set the URL mapping to `\`. For this select `/HelloWorldServlet` in the **URL mappings** field and choose **Edit**.

    ![create servlet wizard](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

9. In the **Pattern** field, replace the current value with just `/`. Confirm with **OK**.

    ![URL mapping](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)
 
10. Click **Finish** to generate the servlet.

    ![finish servlet wizard](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)

11. The Java Editor will open the corresponding `HelloWorldServlet` class in the editor pane. You will also find the `Servlet` under the **`helloworld` project node > Java Resources > `src` > `helloworld` > `HelloWorldServlet.java`**

    ![servlet in editor](http://go.sap.com/dam/application/imagelibrary/photos/276000/276640.jpg.adapt.450_255.false.jpg)
    
12. Next, you will edit the Servlet to output the classical "Hello World". For this you will modify the `doGet()` method and add the following code and save your changes.


    ```java
    /**
     * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
     */
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.getWriter().println("Hello World!");
    }
    ```



    The application is now ready to run.

13. To test your application before deploying it to the SAP HANA Cloud Platform you can run it on a local runtime. To do this, do the following:

    Navigate to your `HelloWorldServlet.java` via the **`helloworld` project node > Java Resources > `src` > `helloworld` > `HelloWorldServlet.java`**. Open the context menu on the `Servlet` with a right-click and choose the **Run on Server** option.



14. Make sure that **Manually define a new server** is selected and choose **SAP > Java Web Server** as server type. Leave all other settings unchanged and click **Finish**.


15. A local server will start with your `helloworld` application deployed. After the server is ready your application will be opened in a browser within Eclipse and greet you with "Hello World!". In the **Servers** view you can also see the running server with your application deployed.


16. To run your application on the SAP HANA Cloud Platform you will choose a different server to run it. Again, navigate to your `HelloWorldServlet.java` via the **`helloworld` project node > Java Resources > `src` > `helloworld` > `HelloWorldServlet.java`**. Open the context menu on the Servlet with a right-click and choose the **Run on Server** option.


17. As before, make sure that **Manually define a new server** is selected. This time choose **SAP > SAP HANA Cloud Platform** as server type. Make sure to set the **Landscape host** to `hanatrial.ondemand.com`. Leave all other settings unchanged and choose Next.


    > Note: The used Landscape host `hanatrial.ondemand.com` is only valid if you are using a free Developer Account. Please change the landscape host if you want to use a productive account. The respective landscape hosts can be found in the [official documentation](https://help.hana.ondemand.com/help/frameset.htm?e4986153bb571014a2ddc2fdd682ee90.html).
    
    
18. On the next wizard page specify the Application name to be `helloworld`, provide the login information for your SAP HANA Cloud Platform account and click **Finish**:

    Field Name     | Value
    :------------- | :-------------
    Account Name   | Your SAP HANA Cloud Platform account name, for example `p1234567890trial`
    Username       | Your SAP HANA Cloud Platform account name, for example `p1234567890` and your password 


19. A Cloud server will start that has your `helloworld` application deployed. After the server is ready your application will be opened in a browser in Eclipse and greet you with Hello World!. In the **Servers** view you can also see the running server with your application deployed


    Congratulations: You have your first application running on the SAP HANA Cloud Platform!


### Optional
Now that you are familiar with the basic routine of developing applications and deploying them locally and to the cloud, you may want to check out the [samples](https://help.hana.ondemand.com/help/frameset.htm?937ce0d172bb101490cf767db0e91070.html) provided as part of the SAP HANA Cloud Platform SDK.

Related Information

 - (Official documentation) [Deploying Applications](https://help.hana.ondemand.com/help/frameset.htm?e5dfbc6cbb5710149279f67fb43d4e5d.html)
 - (Official documentation) [Deploying Locally from Eclipse IDE](https://help.hana.ondemand.com/help/frameset.htm?0f16c9db4a9c407abb1b4987c0afe714.html)
 - (Official documentation) [Deploying on the Cloud from Eclipse IDE](https://help.hana.ondemand.com/help/frameset.htm?60ab35d9edde43a1b38cf48174a3dca2.html)
 - (Official documentation) [SDK Samples](https://help.hana.ondemand.com/help/frameset.htm?937ce0d172bb101490cf767db0e91070.html)


## Next Steps
 - Select a tutorial from the [Tutorial Navigator](http://go.sap.com/developer/tutorial-navigator.html) or the [Tutorial Catalog](http://go.sap.com/developer/tutorials.html)
