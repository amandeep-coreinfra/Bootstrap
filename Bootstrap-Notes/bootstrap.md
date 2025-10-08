## BooStrap Overview

what is bootstrap?
It is an orchestrator that start-stops the processes(background, forground)/services in syncronized manner.

## Flow Diagram:
![Flow Diagram](../Images/SystemStartupContextDiagram.png)

In the Digram above:
## Processmanager: 
It is the lowest level (it is window service), that provides the interfaces to start-stop the processes/services. And you can configure how you can start/stop processes.

Bootstrap is also a window service, that is client of processmanager.

## Bootstrap Service Role:
Bootstrap acts as the "brain" that manages startup sequences intelligently:
- **Startup Management**: Controls background and interactive process startup order
- **Dependency Control**: Ensures background services start before interactive ones
- **Crash Handling**: Monitors process health and handles failures
- **Process Orchestration**: Communicates with Process Manager to start/stop processes (e.g., "start process A")
- **Post-Startup Management**: Continues monitoring and managing processes after they start

*Key point* So here Process Manager is the one who actually starts/stops the processes, but Bootstrap tells Process Manager when and which processes to start/stop based on dependencies and system state.
