# Limit-service
1. Limit-service is one of the service of an application which does limit calculation like minimum and maximum.
2. It's url http://localhost:8080/getLimit. It would execute on 8080 port
3. While configuring any microservices application make sure you are declaring two thing in configuration file
    1. Application Name (EX: spring.application.name=Limit-Service).
    2. Port number (server.port:8080).<br/>
        Note: 8080 is a default port number for tomcat server in SpringBoot application.
4.To read the properties file value from properties file we need one pojo java class with exactly variable what variable we have in properties file . Java class should be annotated with <b>@Component and @ConfigurationProperties </b>and we will send param/value whatever we are taking prefix in properties file.<br>
  
  <b>Example :</b> 
		@Component<br/>
		@ConfigurationProperties("limit-service")<br/>
		public class Configuration {<br/>		
		private int minimum;<br/>
		private int maximum;<br/>
}<br/>		
		properties file value<br/>		
		limit-service.minimum = 99<br/>
		limit-service.maximum =9999<br/>
    
# To register Microservices with config server we have to do
 1. Rename application.properties (Example: abc.properties)
 2. Need to give config server uri in abc.properties<br/>
     <b>Example:</b> spring.cloud.config.uri = http://localhost:8888 (URI of config server)<br/>
    
 <b>Note:</b> 1. If value is not displaying perfectly check profile in services or key of properties file or @ConfigurationProperties param value.
              2. If we comment any properties key value it would pick up default value
     

    
