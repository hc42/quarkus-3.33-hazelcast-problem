# vertx-hazelcast-problem

Reproducer for Quarkus 3.33.1 build problem with vertx-hazelcast.

Maven package leads to:

[ERROR] Failed to execute goal io.quarkus.platform:quarkus-maven-plugin:3.33.1:build (default) on project vertx-hazelcast-problem: Failed to build quarkus application: io.quarkus.builder.BuildException: Build failure: Build failed due to errors
[ERROR] 	[error]: Build step io.quarkus.deployment.steps.MainClassBuildStep#build threw an exception: java.lang.RuntimeException: Failed to record call to method public java.util.function.Supplier io.quarkus.vertx.core.runtime.VertxCoreRecorder.configureVertx(io.quarkus.runtime.LaunchMode,io.quarkus.runtime.ShutdownContext,java.util.List,java.util.List,java.util.List,java.util.concurrent.ExecutorService)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.writeBytecode(BytecodeRecorderImpl.java:493)
[ERROR] 	at io.quarkus.deployment.steps.MainClassBuildStep.writeRecordedBytecode(MainClassBuildStep.java:554)
[ERROR] 	at io.quarkus.deployment.steps.MainClassBuildStep.build(MainClassBuildStep.java:328)
[ERROR] 	at java.base/java.lang.invoke.MethodHandle.invokeWithArguments(MethodHandle.java:735)
[ERROR] 	at io.quarkus.deployment.ExtensionLoader$3.execute(ExtensionLoader.java:898)
[ERROR] 	at io.quarkus.builder.BuildContext.run(BuildContext.java:242)
[ERROR] 	at org.jboss.threads.ContextHandler$1.runWith(ContextHandler.java:18)
[ERROR] 	at org.jboss.threads.EnhancedQueueExecutor$Task.doRunWith(EnhancedQueueExecutor.java:2651)
[ERROR] 	at org.jboss.threads.EnhancedQueueExecutor$Task.run(EnhancedQueueExecutor.java:2630)
[ERROR] 	at org.jboss.threads.EnhancedQueueExecutor.runThreadBody(EnhancedQueueExecutor.java:1622)
[ERROR] 	at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.run(EnhancedQueueExecutor.java:1589)
[ERROR] 	at java.base/java.lang.Thread.run(Thread.java:1474)
[ERROR] 	at org.jboss.threads.JBossThread.run(JBossThread.java:501)
[ERROR] Caused by: java.lang.RuntimeException: java.lang.RuntimeException: Cannot serialise field 'active' on object 'io.vertx.spi.cluster.hazelcast.HazelcastClusterManager@5f928fae' as the property is read only
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadComplexObject(BytecodeRecorderImpl.java:1370)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadObjectInstanceImpl(BytecodeRecorderImpl.java:985)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadObjectInstance(BytecodeRecorderImpl.java:599)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadComplexObject(BytecodeRecorderImpl.java:1143)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadObjectInstanceImpl(BytecodeRecorderImpl.java:985)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadObjectInstance(BytecodeRecorderImpl.java:599)
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.writeBytecode(BytecodeRecorderImpl.java:488)
[ERROR] 	... 12 more
[ERROR] Caused by: java.lang.RuntimeException: Cannot serialise field 'active' on object 'io.vertx.spi.cluster.hazelcast.HazelcastClusterManager@5f928fae' as the property is read only
[ERROR] 	at io.quarkus.deployment.recording.BytecodeRecorderImpl.loadComplexObject(BytecodeRecorderImpl.java:1361)
[ERROR] 	... 18 more
[ERROR] -> [Help 1]
