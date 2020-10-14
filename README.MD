# spring-boot-processes-error

Running the application from IDE (IntelliJ) works. Building + Running the jar fails.
```
2020-10-14 13:15:27.327  INFO 17188 --- [           main] org.camunda.bpm.container                : ENGINE-08023 Deployment summary for process archive 'Demo: Deploying process error':
        processes/hello_world.bpmn
        BOOT-INF/classes/processes/hello_world.bpmn
2020-10-14 13:15:27.552 ERROR 17188 --- [           main] org.camunda.bpm.engine.context           : ENGINE-16004 Exception while closing command context: The deployment contains definitions with the same key 'Process_0un69zw' (id attribute), this is not allowed
```

As soon as the explicit `<resource/>` in `processes.xml` is removed everything works as expected.

#### Reasoning behind processes.xml
When having multiple process-applications on the same process-engine Cockpit shows each deployment as `SpringAutoDeployment`
making it hard to differentiate which application provided which deployment.