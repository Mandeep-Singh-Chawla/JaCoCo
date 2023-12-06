**Steps to find Automation code coverage using JaCoCo**

a) **Prerequisite**:

a) Login to Application server with sudo user
b) Create a directory for Jacoco
c) Download jacocoagent.jar and jacococli.jar from https://www.jacoco.org/jacoco/




b) **Start the Server with JaCoCo Agent:**

1) Use this command to start your application with the JaCoCo agent:
***Java -javaagent:lib/jacocoagent.jar=address=*,port=36320,destfile=jacoco-it.exec,output=tcpserver /path/to/your-web-app.war(.jar)**
2) Replace /path/to/jacocoagent.jar with the actual path of JaCoCo agent JAR.
3) Replace /path/to/your-web-app.war(.jar) with the path of your Application file.
4) This command starts your web application with the JaCoCo agent and specifies the destination file (destfile=jacoco-it.exec) where JaCoCo will store the coverage data.




c) **Perform Actions on the Web Application:**

Once the server is running, perform actions(run automation scripts) on your application to exercise the code you want to cover.




d) **Dump Coverage Data:**

1) Use this JaCoCo command to dump the coverage data:
**java -jar /path/to/jacococli.jar dump --address localhost --port 36320 --destfile jacoco-server.exec**
2) Replace /path/to/jacococli.jar with the actual path of JaCoCo CLI JAR.
3) Adjust --address and --port if you have configured the JaCoCo agent with a different address and port.




e) **Generate Reports:**

1) Use this JaCoCo command to generate HTML reports:
**java -jar /path/to/jacococli.jar report jacoco-server.exec --classfiles /path/to/your/classes --sourcefiles /path/to/your/source --html report**
2) Replace /path/to/jacococli.jar with the actual path of JaCoCo CLI JAR.
3) Replace /path/to/your/classes with the path of your compiled Application classes(till /classes/com).
4) Replace /path/to/your/source with the path of your source Application code(till /src/main/java).




f) **Open html report**

1) Copy report folder to local
2) Click on index.html inside report folder


