#  api-samples-soap
## SOAP API example built for Liberty Java buildpack on IBM Cloud 
#####  3 May 2018 - warrenf

This sample application returns a list of inventory items from a SOAP API. The application is a Java EE 7 Web application with JAX-WS, JAX-RS, and JAXB features.

You can test a deployed copy of this API on IBM Cloud: https://soapsample.mybluemix.net/

To run a local copy of the `ItemServiceApp` application:

1. Install `Maven` on your computer. 
2. Run `mvn liberty:start-server`.

To deploy the `ItemServiceApp` application on to IBM Cloud:

2. Log into your IBM Cloud account with the CLI.
3. Run `bx cf push` to deploy the web application into a Liberty Java buildpack.
4. Run `bx cf set-env ItemServiceApp JBP_CONFIG_LIBERTY "app_archive: {features: [servlet-3.1, jaxrs-2.0, jaxws-2.2, jaxb-2.2, appstate-2.0]}"` to override the default feature set.
5. Run `cf restage` to enable the features in the Liberty buildpack.
