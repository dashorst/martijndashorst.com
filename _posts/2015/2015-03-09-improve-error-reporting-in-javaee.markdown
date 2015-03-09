---
layout: post
status: publish
published: true
title: Improve Error Reporting in Java EE
---

While I am a great advocate of adopting standards and have come to 
dislike ducttaped together solutions of the years, I still have some
qualms with Java (EE) in general and WildFly in particular. 

My number one dislike is the error reporting during deployment. These
are inscrutable, unsolvable, unhelpful messages that are complete and
utter gibberish. If there should be one fricking standard that should
be adopted for Java EE 8 it should be better, standardized error
reporting.

Exhibit A:

<pre lang="java">
14:47:37,980 ERROR [org.jboss.msc.service.fail] (MSC service thread 1-15) MSC000001: Failed to start service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".PARSE: org.jboss.msc.service.StartException in service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".PARSE: JBAS018733: Failed to process phase PARSE of subdeployment "eduarte-common-dao-2.42-SNAPSHOT.jar" of deployment "eduarte-deliverable-dev-ear.ear"
	at org.jboss.as.server.deployment.DeploymentUnitPhaseService.start(DeploymentUnitPhaseService.java:166) [wildfly-server-8.1.0.Final.jar:8.1.0.Final]
	at org.jboss.msc.service.ServiceControllerImpl$StartTask.startService(ServiceControllerImpl.java:1948) [jboss-msc-1.2.2.Final.jar:1.2.2.Final]
	at org.jboss.msc.service.ServiceControllerImpl$StartTask.run(ServiceControllerImpl.java:1881) [jboss-msc-1.2.2.Final.jar:1.2.2.Final]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142) [jrebel-bootstrap-a53fd962a83484078782af30d2cabc06.jar:1.8.0_31]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617) [jrebel-bootstrap-a53fd962a83484078782af30d2cabc06.jar:1.8.0_31]
	at java.lang.Thread.run(Thread.java:745) [jrebel-bootstrap-a53fd962a83484078782af30d2cabc06.jar:]
Caused by: org.jboss.msc.service.ServiceNotFoundException: Service service jboss.ejb.default-resource-adapter-name-service not found
	at org.jboss.msc.service.ServiceContainerImpl.getRequiredService(ServiceContainerImpl.java:668) [jboss-msc-1.2.2.Final.jar:1.2.2.Final]
	at org.jboss.as.ejb3.deployment.processors.MessageDrivenComponentDescriptionFactory.getDefaultResourceAdapterName(MessageDrivenComponentDescriptionFactory.java:278)
	at org.jboss.as.ejb3.deployment.processors.MessageDrivenComponentDescriptionFactory.processMessageBeans(MessageDrivenComponentDescriptionFactory.java:155)
	at org.jboss.as.ejb3.deployment.processors.MessageDrivenComponentDescriptionFactory.processAnnotations(MessageDrivenComponentDescriptionFactory.java:82)
	at org.jboss.as.ejb3.deployment.processors.AnnotatedEJBComponentDescriptionDeploymentUnitProcessor.processAnnotations(AnnotatedEJBComponentDescriptionDeploymentUnitProcessor.java:58)
	at org.jboss.as.ejb3.deployment.processors.AbstractDeploymentUnitProcessor.deploy(AbstractDeploymentUnitProcessor.java:81)
	at org.jboss.as.server.deployment.DeploymentUnitPhaseService.start(DeploymentUnitPhaseService.java:159) [wildfly-server-8.1.0.Final.jar:8.1.0.Final]
	... 5 more
</pre>

And a couple of hundred lines below:

<pre lang="java">
14:47:42,608 ERROR [org.jboss.as.controller.management-operation] (Controller Boot Thread) JBAS014613: Operation ("deploy") failed - address: ([("deployment" => "eduarte-deliverable-dev-ear.ear")]) - failure description: {"JBAS014671: Failed services" => {"jboss.deployment.subunit.\"eduarte-deliverable-dev-ear.ear\".\"eduarte-common-dao-2.42-SNAPSHOT.jar\".PARSE" => "org.jboss.msc.service.StartException in service jboss.deployment.subunit.\"eduarte-deliverable-dev-ear.ear\".\"eduarte-common-dao-2.42-SNAPSHOT.jar\".PARSE: JBAS018733: Failed to process phase PARSE of subdeployment \"eduarte-common-dao-2.42-SNAPSHOT.jar\" of deployment \"eduarte-deliverable-dev-ear.ear\"
    Caused by: org.jboss.msc.service.ServiceNotFoundException: Service service jboss.ejb.default-resource-adapter-name-service not found"}}
14:47:42,642 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 28) JBAS018559: Deployed "eduarte-portal-eo-student.war" (runtime-name : "eduarte-portal-eo-student.war")
14:47:42,642 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 28) JBAS018559: Deployed "eduarte-portal-eo-ouder.war" (runtime-name : "eduarte-portal-eo-ouder.war")
14:47:42,642 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 28) JBAS018559: Deployed "eduarte-portal-eo-docent.war" (runtime-name : "eduarte-portal-eo-docent.war")
14:47:42,642 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 28) JBAS018559: Deployed "eduarte-portal-eo-bedrijf.war" (runtime-name : "eduarte-portal-eo-bedrijf.war")
14:47:42,643 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 28) JBAS018559: Deployed "eduarte-portal-eo-authenticator.war" (runtime-name : "eduarte-portal-eo-authenticator.war")
14:47:42,643 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 28) JBAS018559: Deployed "eduarte-deliverable-dev-ear.ear" (runtime-name : "eduarte-deliverable-dev-ear.ear")
14:47:42,644 INFO  [org.jboss.as.controller] (Controller Boot Thread) JBAS014774: Service status report
JBAS014777:   Services which failed to start:      service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".PARSE: org.jboss.msc.service.StartException in service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".PARSE: JBAS018733: Failed to process phase PARSE of subdeployment "eduarte-common-dao-2.42-SNAPSHOT.jar" of deployment "eduarte-deliverable-dev-ear.ear"

14:47:42,653 INFO  [org.jboss.as] (Controller Boot Thread) JBAS015961: Http management interface listening on http://127.0.0.1:9990/management
14:47:42,653 INFO  [org.jboss.as] (Controller Boot Thread) JBAS015951: Admin console listening on http://127.0.0.1:9990
14:47:42,654 ERROR [org.jboss.as] (Controller Boot Thread) JBAS015875: WildFly 8.1.0.Final "Kenny" started (with errors) in 22967ms - Started 1208 of 1315 services (4 services failed or missing dependencies, 225 services are lazy, passive or on-demand)
14:47:42,936 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-13) JBAS015974: Stopped subdeployment (runtime-name: eduarte-common-dao-2.42-SNAPSHOT.jar) in 38ms
14:47:42,942 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-7) JBAS015974: Stopped subdeployment (runtime-name: eduarte-ws-eo-rest-2.42-SNAPSHOT.war) in 44ms
14:47:43,054 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-6) JBAS015974: Stopped subdeployment (runtime-name: eduarte-sis-web-main.war) in 156ms
14:47:43,088 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-9) JBAS015877: Stopped deployment eduarte-deliverable-dev-ear.ear (runtime-name: eduarte-deliverable-dev-ear.ear) in 195ms
14:47:43,136 INFO  [org.jboss.as.server] (DeploymentScanner-threads - 2) JBAS018558: Undeployed "eduarte-deliverable-dev-ear.ear" (runtime-name: "eduarte-deliverable-dev-ear.ear")
14:47:43,137 INFO  [org.jboss.as.controller] (DeploymentScanner-threads - 2) JBAS014774: Service status report
JBAS014777:   Services which failed to start:      service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".PARSE

14:47:47,715 WARN  [org.jboss.as.server.deployment.scanner] (DeploymentScanner-threads - 2) JBAS015002: Deployment of 'eduarte-web-main.war' requested, but the deployment is not present
14:47:47,715 INFO  [org.jboss.as.server.deployment.scanner] (DeploymentScanner-threads - 2) JBAS015003: Found eduarte-deliverable-dev-ear.ear in deployment directory. To trigger deployment create a file called eduarte-deliverable-dev-ear.ear.dodeploy
</pre>

Apparently something is missing, but the stack traces don't contain any code that is under my 
purview, and the error message is really clear and helpful in identifying what is missing:

> MSC000001: Failed to start service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".
> PARSE: org.jboss.msc.service.StartException in service jboss.deployment.subunit."eduarte-deliverable-dev-ear.ear"."eduarte-common-dao-2.42-SNAPSHOT.jar".
> PARSE: JBAS018733: Failed to process phase PARSE of subdeployment "eduarte-common-dao-2.42-SNAPSHOT.jar" of deployment "eduarte-deliverable-dev-ear.ear"

Which is caused by:

> org.jboss.msc.service.ServiceNotFoundException: Service service jboss.ejb.default-resource-adapter-name-service not found

What the hell is Wildfly trying to tell me?

The solution (of course) is to run the configuration script that is external to our application,
in order to tell Wildfly that a new message queue should be added:

<pre lang="java">
15:03:30,952 WARN  [org.jboss.messaging] (management-handler-thread - 2) JBAS011618: There is no resource matching the expiry-address jms.queue.ExpiryQueue for the address-settings #, expired messages from destinations matching this address-setting will be lost!
15:03:30,952 WARN  [org.jboss.messaging] (management-handler-thread - 2) JBAS011619: There is no resource matching the dead-letter-address jms.queue.DLQ for the address-settings #, undelivered messages from destinations matching this address-setting will be lost!
15:03:31,033 WARN  [org.jboss.as.messaging] (MSC service thread 1-16) JBAS011600: AIO wasn't located on this platform, it will fall back to using pure Java NIO. If your platform is Linux, install LibAIO to enable the AIO journal
15:03:31,149 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221000: live server is starting with configuration HornetQ Configuration (clustered=false,backup=false,sharedStore=true,journalDirectory=/Users/dashorst/Workspaces/luna/wildfly-8.1.0.Final/standalone/data/messagingjournal,bindingsDirectory=/Users/dashorst/Workspaces/luna/wildfly-8.1.0.Final/standalone/data/messagingbindings,largeMessagesDirectory=/Users/dashorst/Workspaces/luna/wildfly-8.1.0.Final/standalone/data/messaginglargemessages,pagingDirectory=/Users/dashorst/Workspaces/luna/wildfly-8.1.0.Final/standalone/data/messagingpaging)
15:03:31,151 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221006: Waiting to obtain live lock
15:03:31,222 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221013: Using NIO Journal
15:03:31,288 INFO  [io.netty.util.internal.PlatformDependent] (ServerService Thread Pool -- 72) Your platform does not provide complete low-level API for accessing direct buffers reliably. Unless explicitly requested, heap buffer will always be preferred to avoid potential system unstability.
15:03:31,359 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221043: Adding protocol support CORE
15:03:31,372 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221043: Adding protocol support AMQP
15:03:31,380 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221043: Adding protocol support STOMP
15:03:31,427 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221034: Waiting to obtain live lock
15:03:31,428 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221035: Live Server Obtained live lock
15:03:31,610 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221007: Server is now live
15:03:31,610 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 72) HQ221001: HornetQ Server version 2.4.1.Final (Fast Hornet, 124) [1141831d-c665-11e4-86db-0ffb92fb33f7] 
15:03:31,666 INFO  [org.jboss.as.messaging] (ServerService Thread Pool -- 72) JBAS011601: Bound messaging object to jndi name java:/messaging/ConnectionFactory
15:03:31,672 INFO  [org.hornetq.core.server] (ServerService Thread Pool -- 73) HQ221003: trying to deploy queue jms.queue.eventQueue
15:03:31,785 INFO  [org.jboss.as.messaging] (ServerService Thread Pool -- 73) JBAS011601: Bound messaging object to jndi name queue/eventQueue
15:03:31,820 INFO  [org.jboss.as.connector.deployment] (MSC service thread 1-10) JBAS010406: Registered connection factory java:/messaging/JmsXA
15:03:31,908 INFO  [org.hornetq.ra] (MSC service thread 1-10) HornetQ resource adaptor started
15:03:31,908 INFO  [org.jboss.as.connector.services.resourceadapters.ResourceAdapterActivatorService$ResourceAdapterActivator] (MSC service thread 1-10) IJ020002: Deployed: file://RaActivatorhornetq-ra
15:03:31,910 INFO  [org.jboss.as.connector.deployment] (MSC service thread 1-5) JBAS010401: Bound JCA ConnectionFactory [java:/messaging/JmsXA]
15:03:31,910 INFO  [org.jboss.as.messaging] (MSC service thread 1-16) JBAS011601: Bound messaging object to jndi name java:jboss/DefaultJMSConnectionFactory
</pre>

Unfortunately the original error message did not provide any useful insights as to what was missing.
