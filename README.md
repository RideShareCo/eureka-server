# eureka-server
Eureka Server is primarily used  for locating services for the purpose of load balancing and failover of middle-tier servers

Shall run:
java -Dspring.profiles.active=profile -jar eureka-server-version.jar --server.port=Port_desired

For example, for one single instance completely standalone:
java -jar eureka-server-1.0.0.jar

For cluster eureka server, shall run primary, secondary, and tertiary profiles illustrate running 3 intercommunicating instances.  This example has them running
# side-by-side on localhost -- which is unrealistic in production -- but does illustrate how multiple instances collaborate.
# Run by opening 3 separate command prompts:

java -Dspring.profiles.active=primary -jar eureka-server-1.0.0.jar --server.port=8013
java -Dspring.profiles.active=secondary -jar eureka-server-1.0.0.jar --server.port=8013
java -Dspring.profiles.active=tertiary -jar eureka-server-1.0.0.jar --server.port=8013


