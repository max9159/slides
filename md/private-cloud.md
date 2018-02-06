# Private Cloud

---

## Issues

1. Slow for applying resource and adjust settings
1. Unable to know Server/Application status
1. Difficult to build new environment

Note:
- Difficult to build new environment - 1~2 day(s)
    - Apply new server required effort for finding last apply info and reinstall every software and settings
    - Although VM image template could achieve the same goal, MIS is unable to maintain all BU's image. By using private cloud IT could maintain their own image in version control
- Slow for applying resource and adjust settings - MIS-1241 (5 days),  MIS-1230 (1 month)
    - too many processes (Finding document, inaccurate assessment, Approve flow, Server spec adjustment multiple times, firewall....)
    -  Limited resource and free but unreleased resource lead to tight assessment and bargain. It caused more repeated flow
- Unable to know Server/Application status 
    - e.g. After QAT deployment required one by one manually check

---

## Phases

1. Build a private cloud for experimental side projects
    - ETA : 2 week
    - Resolve Issue : Unable to know Server/Application status
    - Require resource : 2 linux + 2 windows machine

1. Integrate monitoring and docker into private cloud
    - ETA : 2 week
    - Resolve Issue : Unable to know Server/Application status
    - Require resource : docker resource

1. Enhance private cloud to team's QAT level
    - ETA : 1 month
    - Resolve Issue : Difficult to build new environment
    - Require resource : transfer teams QAT resource into private cloud

---

## Member

- Andy Chen
- Max Chen
- Jamie Chien
- Max Chou
- Alex

---

## Q & A

---

## Thank you