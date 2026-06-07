# Software Testing - Mind Map

```
+=========================================================================================================+
|                                    SOFTWARE TESTING — MIND MAP                                          |
+========================================================================================================+


                                +==================================+
                                |        SOFTWARE TESTING          |
                                +==================================+
                                       |
         +-----------------------------+-----------------------------+
         |                             |                             |
         v                             v                             v
+------------------+      +------------------------+      +------------------------+
|      GOALS       |      |   V & V FOUNDATION     |      |       PROCESS          |
+------------------+      +------------------------+      +------------------------+
         |                             |                             |
    +----+----+                  +-----+-----+                +-----+------+
    |         |                  |           |                |            |
    v         v                  v           v                v            v
+---------+---------+     +-------------+-------------+  +----------+-----------+
|VALIDATION| DEFECT  |     |VERIFICATION|  VALIDATION  |  |TEST PLAN |TEST CASE  |
|          | TESTING |     |            |              |  |          |SPEC.      |
+---------+---------+     +-------------+-------------+  +----------+-----------+
    |         |                  |           |                |            |
    |         |           "Built right?"   "Right            |            |
    |    +----+----+      +----+----+      product?"         |            |
    |    |         |      |         |             |     What/When/     Inputs/
    v    v         v      v         v             v     Who/Resources  Expected
+------+  +-------+   +------+   +--------+  +----------+    |       outputs
|Demon.|  |Discover|   |Confor|   |  Meets |  | User test|    |            |
|require|  | faults |   |ms to |   |  user  |  |Acceptance|TEST PLAN    |
|ments  |  |        |   |specif|   |  needs |  | testing  |Schedule    v
|are met|  |Success|   |      |   |        |  +----------+Resources    +----+
|      |  | test =|   |Inspec|   |Static  |                             |COMP|
|Succes|  | finds |   |tions |   |analys +                             |ARE  |
| test=|  | defect|   |      |   |        |                             | TO  |
|no    |  +-------+   |Static|   +--------+                             |EXPE|
|failur|               |analys|                                         |CTAT|
+------+               |(no   |                                         |IONS|
                       |exec) |                                         |    |
                       +------+                                         |TEST|
                          |                                              |REPO|
       +------------------+                                              |RTS |
       |         |         |                                             +----+
       v         v         v
   +---------+--------+----------+
   |Can catch|Catches | Broader  |
   |spec gaps|interact| quality  |
   |         |between |(portab., |
   |         |errors  |maintain.)|
   +---------+--------+----------+


         |                                                             |
         |                                                             |
         +----------------------------+--------------------------------+
                                      |
                                      v
                    +----------------------------+
                    |      TESTING LEVELS        |
                    +----------------------------+
                                      |
    +-----------------------------+   +--------------------------------+
    |                             |   |                                |
    v                             v   v                                v
+--------------------+    +-----------------+     +-----------------------------+
| DEVELOPMENT TESTING|    |  USER TESTING   |     |       TECHNIQUES            |
+--------------------+    +-----------------+     +-----------------------------+
    |                             |                              |               |
+---+----+--------+-------+ +----+-----+              +----------+----+  +------+-------+
|   |    |        |       | |    |     |              |             |  |              |
v   v    v        v       v v    v     v              v             v  v              v
+--+ +------+ +------+ +--+ +---++---+ +------+  +-----------+ +--------+  +-----------+---------+
|UNIT |COMPON.| SYSTEM|REL |ALPHA|BETA|ACCEPT. |  | BLACK-BOX | |WHITE-BOX|  |OTHER TECHNIQUES    |
+--+  +------+ +------+ +--+  |    |   +------+  +-----------+ +--------+  +-----------+---------+
|   |         |       |    |  |    |   |        |  |           | |         |             |       |
Sin. Integ.  Whole  Sep. At   At   For  |      No code     Full code   |             |
gle   units   system team dev. user mal  |     access        access     |             |
unit   focus   focus  focus site site sig.|        |             |       |             |
|    |         |       |    |  |    |   |  Derived from   Derived from  |             |
Def. Interf. Interf.    |Contr.Real Cont.|      spec         logic      |             |
e  |         |       |  |enviro|world|  |        |             |       |             |
c  |         |       |  +------+-----+  |  +------+------+ +---+------+  |             |
u  |         |       |              |   |  |             | |          |  |             |
s  |         |       |        RELEASE|   |  v             v v          v  |             |
   |         |       |        TESTING|   |+---------+ +---------+  +----+----+  +----+----+
   |         |       |             | |   ||Equiv.   | |Boundary |  |Statement|  | Error   |
   |         |       |        +----+-+   ||Partit.  | |Value    |  |Coverage |  | Guessing|
   |         |       |        |        |   ||         | |Analysis |  +---------+  +----+----+
   |         |       |        |Release |   |+---------+ +---------+       |             |
   |         |       |        |Cand.   |   |                          +---+---+   +----+------+
   |         |       |        |        |   |                          |Branch  |   |Experience |
   |         |       |        +--------+   |                          |Coverage|   |-based     |
   |         |       |          |          |                          +---+---+   |           |
   |         |       |    +-----+-----+    |                              |       |Common     |
   |         |       |    |    |      |    |                          +---+--+    |weak spots |
   |         |       |    |    |      |    |                          | Path  |    | - Zero inp|
   |         |       |  +--+ +-+--+ +--+  |                          |Coverag|    | - Large # |
   |         |       |  |Fnc| |Rel | |Perf|                          +---+--+    | - Alpha   |
   |         |       |  |   | |    | |    |                              |       |   in num. |
   |         |       |  |Tst| |Tst | |Tst |                              v       | - Empty   |
   |         |       |  +---+ +----+ +----+                         +-----------+ |   arrays  |
   |         |       |         |                                     |PATH TEST | |           |
   |         |       |    +----+----+                                |(Basis)   | |Complement|
   |         |       |    | Customer |                                +-----------+ | formal    |
   |         |       |    |  Usage   |                                     |       | technique |
   |         |       |    +---------+                                 +----+----+  +-----------+
   |         |       |                                               |         |
   |         |       |                                         +----+---+ +---+------+
   |         |       |                                         |Control | |Cyclomatic|
   |         |       |                                         |Flow    | |Complexity|
   |         |       |                                         |Graph   | |M=E-N+2   |
   |         |       |                                         +--------+ +----------+

                           |
                           |
                    +------+----------------------------+
                    |                                  |
                    v                                  v
        +------------------------+       +--------------------------+
        |  PENETRATION TESTING   |       |  TDD (TEST-DRIVEN DEV.)  |
        +------------------------+       +--------------------------+
        |                        |       |                          |
        | Security-focused       |       |   RED-GREEN-REFACTOR     |
        | Exploit vulnerabilities|       |   +--------+--------+    |
        | - Software weaknesses  |       |   |        |        |    |
        | - Hardware weaknesses  |       |   v        v        v    |
        | - Organisational       |   +--------+ +--------+ +------+ |
        |   weaknesses           |   | Write  | |Implem.| |Refact| |
        |                        |   | test(= | |ent code| |or    | |
        | Cannot prove security  |   | fails) | |(pass)  | |code  | |
        +------------------------+   +--------+ +--------+ +------+ |

                           BENEFITS:
                       +---------+---------+---------+--------+
                       |  Code   |Regress. | Simplif.| Living |
                       |Coverage |Test Suit|Debugging|  Doc.  |
                       |         |(grows w/|(bug in  |        |
                       |         |codebase)|recent   |        |
                       |         |         | code)   |        |
                       +---------+---------+---------+--------+


                           |
                           |
                    +------+-----------------------------------------+
                    |                                                |
                    v                                                v
        +----------------------------------+       +------------------------------------+
        |         RELATED TOPICS           |       |          KEY PRINCIPLES            |
        +----------------------------------+       +------------------------------------+
        |                                  |       |                                    |
        |  +----------+  +------------+    |       |  Testing reveals presence of       |
        |  |Requiremts|  |SW Design   |    |       |  errors, NOT their absence         |
        |  |(source of|  |(guides sys |    |       |                                    |
        |  |valid.    |  | & component|    |       |  Absence of evidence is not        |
        |  |tests)    |  | tests)     |    |       |  evidence of absence               |
        |  +----------+  +------------+    |       |  (passing tests != no bugs)        |
        |                                  |       |                                    |
        |  +----------+  +------------+    |       |  Inspections and testing are       |
        |  |Quality   |  |Risk Mgmt   |    |       |  complementary (static + dynamic)  |
        |  |Mgmt      |  |(risk-based |    |       |                                    |
        |  |(QA act., |  |test priorit|    |       +------------------------------------+
        |  |inspect.) |  |ty)         |    |
        |  +----------+  +------------+    |
        |                                  |
        |  +----------+  +------------+    |
        |  |Safety    |  |Reliability |    |
        |  |Testing   |  |Testing     |    |
        |  +----------+  +------------+    |
        |  |Safety case|  |Operational |   |
        |  |must demo  |  |profile     |   |
        |  |no unrecover|  |(usage model)| |
        |  |errors     |  |MTTF, POFOD |   |
        |  +----------+  +------------+    |
        |                                  |
        |  +----------+  +------------+    |
        |  |Info.     |  |Embedded    |    |
        |  |Systems   |  |Systems     |    |
        |  |Testing   |  |Testing     |    |
        |  +----------+  +------------+    |
        |  |Database-  |  |Platform    |   |
        |  |centered   |  |reuse       |   |
        |  |(no data   |  |strategy    |   |
        |  |loss)      |  |Integration |   |
        |  |User inter.|  |testing     |   |
        |  |intensive  |  |Limited     |   |
        |  |(GUI hard) |  |debugging   |   |
        |  +----------+  +------------+    |
        +----------------------------------+
```