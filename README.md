---
config:
  layout: fixed
---
flowchart LR
 subgraph DEV["Development"]
        CSV["CSV"]
        SCRIPT["SCRIPT"]
        BRANCH["BRANCH"]
  end
 subgraph QA["Review"]
        MERGE["MERGE"]
        PR["PR"]
  end
    BRANCH --> SCRIPT
    SCRIPT --> CSV
    CSV --> PR
    PR --> MERGE
    REQ["REQ"] --> TASK["TASK"]
    TASK --> DEV
    MERGE --> RELEASE["RELEASE"]
