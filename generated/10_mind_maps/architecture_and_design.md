# Architecture & Design — Mind Map

```
                                     ARCHITECTURE AND DESIGN
                                             │
        ┌────────────────────────────────────┼────────────────────────────────────┐
        │                                    │                                    │
   DESIGN CONCEPTS                   ARCHITECTURAL                      ARCHITECTURAL
        │                            PATTERNS                              VIEWS
        │                                │                                    │
 ┌──────┼──────┐            ┌────────────┼────────────┐              ┌───────┼───────┐
 │      │      │            │            │             │              │       │       │
CONCEPTS  GOALS  QUALITY   SHARED      VIRTUAL       OTHER         4+1    ISO/IEC  VIEWS &
         │      ATTRIBS    MEMORY      MACHINE      STYLES        MODEL   42010    BEYOND
         │         │          │            │            │              │       │       │
 ┌───────┼───┐  ┌──┴───┐  ┌──┴───┐  ┌───┴───┐    ┌───┴───┐    ┌──────┼──────┐      │
 │       │   │  │      │  │      │  │       │    │       │    │      │      │      │
ABSTRA-  MOD- INFO   FIRM- COM-  PERFOR- LAYERED INTER- CLIENT/ ┌──┴──┐   │   │      │
CTION    ULAR- HIDING NESS  MODITY MANCE   │     PRETER SERVER │  │  │   │   │      │
         ITY           │   │      │         │            │     LOGI- DEVE- │   │      │
COUPLING      │   DELIGHT  SCALA- PIPE-  │            │     CAL   LOP-  │   │      │
   │          │            BILITY  AND-  │            │      │    MENT   │   │      │
  LOW          REFINE-     EXTENSI- FILTER │            │      │     │   │   │      │
COUPLING       MENT        BILITY   │     │            │      │     │   │   │      │
   │            │          │            │            │      │     │   │   │      │
 HIGH          REFAC-  MODIFIA- BLACK-  │         BROAD-  PROC- PHYSI- │   │      │
COHESION       TORING   BILITY   BOARD  │         CAST    ESS    CAL   │   │      │
   │            │          │            │            │      │     │   │   │      │
INFORMA-      OO      TESTA-         │            │      │     │   │   │      │
TIONAL        CON-    BILITY         │            │      │     │   │   │      │
HIDING        CEPTS      │            │            │      │     │   │   │      │
   │            │     REUSA-       │            │      │  SCENA-   │   │      │
DESIGN          │     BILITY       │            │      │   RIOS    │   │      │
CLASSES    ┌────┼────┐  │            │            │      │   (CENTER)│   │      │
   │       │    │    │  SECURITY  │            │      │     │   │   │      │
INTER-  ENCAP- INHER- │            │            │      │     │   │   │      │
FACE     SULA- ITANCE DATA       │            │      │     │   │   │      │
ENTITY   TION         │     INTEGRITY       │            │      │     │   │      │
CONTROL         POLY- │                        │            │      │     │   │      │
FOUNDATION      MORPHISM                        │            │      │     │   │      │
                                                        │            │      │     │   │      │
                                                     APPLICATION    MODULE  C-AND-C ALLOCATION
                                                     ARCHITECTURES    │       │       │
                                                         │         ┌──┼──┐  ┌──┼──┐  ┌──┼──┐
                                                  ┌───────┼───────┐ │  │  │  │  │  │  │  │  │
                                                  │       │       │ DECOMP  USE  LAYERED    │  │  │
                                              CLIENT- THREE-  SOA  │        │        │  │  │
                                              SERVER   TIER        │        │        │  │  │
                                                         │        │        │        │  │  │
                                                    ┌────┼────┐  PIPE-  SHARED LAYERED │  │  │
                                                    │    │    │  AND-   MEMORY        │  │  │
                                               PRESEN- APPLI- DATA  FILTER             │  │  │
                                               TATION  CATION  TIER   │        │        │  │  │
                                                                 CLIENT- COMM-  │  │  │
                                                                 SERVER  UNICAT-  │  │  │
                                                                         ING     │  │  │
                                                                         │        │  │  │
                                                                 DEPLOY- IMPLE- WORK │  │
                                                                 MENT    MENTA- ASSIGN-│
                                                                         TION   MENT



                              ┌─────────────────────────────────────────────────────────┐
                              │                    PATTERN MAP BY CATEGORY              │
                              ├──────────────┬─────────────────┬────────────────────────┤
                              │ SHARED       │ VIRTUAL MACHINE │ OTHER                  │
                              │ MEMORY       │                 │                        │
                              ├──────────────┼─────────────────┼────────────────────────┤
                              │ • Layered    │ • Interpreter   │ • Client/Server        │
                              │ • Pipes &    │                 │ • Broadcast            │
                              │   Filters    │                 │                        │
                              │ • Blackboard │                 │                        │
                              ├──────────────┴─────────────────┴────────────────────────┤
                              │ REPOSITORY           │ CONTROL                           │
                              ├──────────────────────┼──────────────────────────────────┤
                              │ • Database           │ • Process Control                 │
                              │ • Blackboard         │ • Finite State Machine            │
                              └──────────────────────┴──────────────────────────────────┘


                              ┌─────────────────────────────────────────────────────────┐
                              │             4+1 VIEW MODEL — PATTERN MAPPING            │
                              ├────────────┬──────────────┬──────────────┬──────────────┤
                              │  LOGICAL   │ DEVELOPMENT  │   PROCESS    │   PHYSICAL   │
                              │  VIEW      │    VIEW      │    VIEW      │    VIEW      │
                              ├────────────┼──────────────┼──────────────┼──────────────┤
                              │  Façade    │   Layered    │ Pipe-and-    │ Master-Slave │
                              │  Pattern   │   Pattern    │ Filter       │   Pattern    │
                              └────────────┴──────────────┴──────────────┴──────────────┘


                              ┌─────────────────────────────────────────────────────────┐
                              │           ARCHITECTURAL VIEW CATEGORIES                 │
                              ├───────────────┬──────────────────┬──────────────────────┤
                              │    MODULE     │   COMPONENT &    │     ALLOCATION       │
                              │     VIEWS     │    CONNECTOR     │       VIEWS          │
                              │               │      VIEWS       │                      │
                              ├───────────────┼──────────────────┼──────────────────────┤
                              │ • Decompo-    │ • Pipe-and-      │ • Deployment         │
                              │   sition      │   Filter         │   views              │
                              │ • Uses views  │ • Shared-memory  │ • Implementation     │
                              │ • Layered     │ • Layered        │   views              │
                              │   views       │ • Client-server  │ • Work assignment    │
                              │               │ • Communicating  │   views              │
                              │               │   processes      │                      │
                              ├───────────────┴──────────────────┴──────────────────────┤
                              │ USED FOR:    USED FOR:          USED FOR:               │
                              │ Maintain-    Performance,       Software-to-hardware    │
                              │ ability,     Reliability,       mapping                 │
                              │ Portability, Availability                             │
                              │ Reusability                                            │
                              └─────────────────────────────────────────────────────────┘


                              ┌─────────────────────────────────────────────────────────┐
                              │            APPLICATION ARCHITECTURES                    │
                              ├─────────────────┬──────────────────┬────────────────────┤
                              │      SOA        │   MICROSERVICES  │   THREE-TIER       │
                              ├─────────────────┼──────────────────┼────────────────────┤
                              │ Enterprise      │ Cloud-native     │ Web applications   │
                              │ Service Bus     │ API Gateway      │ Presentation tier  │
                              │ (ESB)           │ Message Broker   │ Application tier   │
                              │ UDDI Registry   │ Independent      │ Data tier          │
                              │ Coarse services │ deployment       │                    │
                              │ Shared data     │ Fine services    │                    │
                              │                 │ DB-per-service   │                    │
                              └─────────────────┴──────────────────┴────────────────────┘
```
