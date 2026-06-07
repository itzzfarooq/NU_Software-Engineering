# Load Testing with JMeter — ASCII Mind Map

```
                         +===================================+
                         |      LOAD TESTING with JMETER     |
                         +===================================+
                                       |
         +-----------------------------+-----------------------------+
         |                               |                           |
         v                               v                           v
+===================+         +===================+         +===================+
|   1. PREREQ       |         |   2. SETUP         |         |   3. TEST PLAN     |
|                   |         |                    |         |                    |
| Java 8+ required  |         | Download .zip/.tgz |         | Root element       |
| Check: java -ver  |         | from jmeter.apache  |         | Holds everything   |
+===================+         | Extract to folder  |         +===================+
         |                     | bin/jmeter.bat     |                  |
         |                     | bin/jmeter.sh      |         +--------+--------+
         |                     +====================+         |        |        |
         |                                                    v        v        v
         +--------------------------------------------------->+   +--------+  +--------+
                                                               |   | 4. TG   |  | 5. SAM  |
                                                               |   +--------+  +--------+
                                                               |   Thread Grp  | Samplers |
                                                               |   - # threads | HTTP Req |
                                                               |   - ramp-up   | GET/POST|
                                                               |   - loop cnt  | Server  |
                                                               |               | Path    |
                                                               |               +---------+
                                                               |
                                              +---------------+---------------+
                                              |               |               |
                                              v               v               v
                                        +---------+     +---------+     +-----------+
                                        |6. CNFIG |     |7. TIMER |     |8. LISTENR |
                                        +---------+     +---------+     +-----------+
                                        |Defaults |     |Pacing   |     | Show rslt |
                                        |HTTP Req |     |Think Tm |     +-----------+
                                        +---------+     +---------+          |
                                                                   +---------+---------+
                                                                   |                   |
                                                                   v                   v
                                                            +============+     +============+
                                                            | TABLE VIEW |     | GRAPH VIEW |
                                                            +============+     +============+
                                                            | Per-sample  |     | Avg/Med/Dev|
                                                            | Sample Time |     | Throughput |
                                                            | Latency     |     | Trend line |
                                                            | Bytes       |     | Data points|
                                                            | Status(G/R) |     +============+
                                                            | Connect Tm  |
                                                            +============+

+=============================================================================+
|                JMETER EXECUTION FLOW                                         |
|                                                                             |
|   Start --> Thread Group spawns N threads --> Each thread runs Sampler      |
|   --> Sampler sends HTTP request --> Listener records result --> Repeat     |
|   (until loop count or test stop) --> Stop                                   |
+=============================================================================+

+=============================================================================+
|                KEY METRICS (Exam Focus)                                      |
|                                                                             |
|   Sample Time (ms)  = Total round-trip: request sent --> full response rcvd |
|   Latency (ms)       = Time to first byte of response                       |
|   Connect Time (ms)  = Time to establish TCP connection                     |
|   Throughput         = Requests per unit time (e.g., req/sec)               |
|   Bytes / Sent Bytes = Response & request sizes                             |
+=============================================================================+

+=============================================================================+
|                COMMON MISTAKES / EXAM TRAPS                                  |
|                                                                             |
|   1. No Java installed --> JMeter won't launch                              |
|   2. Using GUI for prod tests --> Memory heavy; use CLI instead             |
|   3. Wrong redirect config --> False failures on 301/302 responses          |
|   4. Ramp-Up = 0 & large thread count --> Server overload on start         |
|   5. Confusing Latency vs Sample Time on exam                               |
|   6. Not saving Test Plan before run --> Risk of losing config             |
+=============================================================================+

+=============================================================================+
|                RELATIONSHIPS                                                 |
|                                                                             |
|   Test Plan                                                                 |
|     |                                                                       |
|     +-- Thread Group (defines users)                                        |
|           |                                                                 |
|           +-- Config Elements (e.g., HTTP Request Defaults)                 |
|           |                                                                 |
|           +-- Samplers (e.g., HTTP Request) ---> sends request to server    |
|           |                                                                 |
|           +-- Listeners (e.g., Table, Graph) <--- captures results          |
|                                                                             |
|   Data flow:                                                                |
|     User action --> Sampler --> Server --> Response --> Listener --> Display|
+=============================================================================+

+=============================================================================+
|                RAMP-UP EXPLANATION                                          |
|                                                                             |
|   50 threads, ramp-up = 25 sec                                              |
|   --> 2 threads start every second                                          |
|   --> Prevents "thundering herd"                                            |
|   --> Reveals gradual degradation                                           |
+=============================================================================+

+=============================================================================+
|                CLI EXECUTION (for real tests)                                |
|                                                                             |
|   jmeter -n -t myplan.jmx -l results.jtl                                    |
|   -n = non-GUI mode                                                         |
|   -t = test plan file                                                       |
|   -l = results log file                                                     |
+=============================================================================+

+=============================================================================+
|                COMPONENT HIERARCHY (Tree View)                              |
|                                                                             |
|   Test Plan (daraz)                                                         |
|   |-- Thread Group                                                          |
|   |   |-- HTTP Request Defaults (server: flex.nu.edu.pk)                    |
|   |   |-- HTTP Request: HomePage (GET /)                                   |
|   |   |-- HTTP Request: MAIN (GET /Home/)                                  |
|   |   |-- View Results in Table (Listener)                                  |
|   |   |-- Graph Results (Listener)                                          |
+=============================================================================+
```