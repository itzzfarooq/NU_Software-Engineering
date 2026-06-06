```
╔══════════════════════════════════════════════════════════════════╗
║                           TESTING TOOLS                          ║
╠══════════════════════════════════════════════════════════════════╣
║  Tools and frameworks for software testing across the lifecycle ║
╚══════════════════════════════════════════════════════════════════╝

  │
  ├── JMeter (Apache) ─────────────────────────────────────────────
  │   ├── Open source Java-based load testing tool
  │   ├── Protocol Support (HTTP, FTP, SOAP, Database, LDAP, TCP)
  │   ├── Test Plan Structure (thread groups, samplers, listeners)
  │   ├── Load Testing Types (performance, stress, endurance, spike)
  │   ├── Benefits (open source, GUI + CLI, extensible, cross-platform)
  │   └── Limitations (resource intensive, no browser simulation)
  │
  ├── Load Testing ────────────────────────────────────────────────
  │   ├── Definition (test system under expected load)
  │   ├── Types (load, stress, endurance, spike, scalability)
  │   ├── Process (define, create scripts, configure, execute, analyze)
  │   └── Key Metrics (response time, throughput, error rate, CPU)
  │
  ├── Other Testing Tools ─────────────────────────────────────────
  │   ├── Selenium (browser automation, cross-browser, WebDriver)
  │   ├── JUnit / TestNG (unit testing, annotations, assertions)
  │   ├── Postman (API / REST testing, collections, environments)
  │   ├── Cypress (end-to-end, time-travel debugging)
  │   └── Appium (mobile, iOS/Android, cross-platform)
  │
  ├── Test Automation Frameworks ──────────────────────────────────
  │   ├── Types (linear, modular, data-driven, keyword, hybrid)
  │   ├── Components (scripts, object repo, test data, reporting)
  │   ├── Benefits (repeatability, speed, consistency, early detection)
  │   └── Challenges (investment, maintenance, expertise)
  │
  ├── Performance Testing Tools ───────────────────────────────────
  │   ├── LoadRunner (enterprise, virtual users, protocol support)
  │   ├── Gatling (Scala-based, high performance, code-based)
  │   ├── Locust (Python-based, distributed, scalable)
  │   └── k6 (JavaScript, developer focused, cloud integration)
  │
  ├── Test Management Tools ───────────────────────────────────────
  │   ├── TestRail (test case management, planning, reporting)
  │   ├── Zephyr (JIRA integration, test cycles, dashboards)
  │   └── qTest (enterprise, requirements traceability)
  │
  ├── Static Analysis Tools ───────────────────────────────────────
  │   ├── SonarQube (code quality, security, technical debt)
  │   ├── ESLint (JavaScript linting, code standards)
  │   └── PMD (source analysis, bug detection, code standards)
  │
  └── Bug Tracking Tools ──────────────────────────────────────────
      ├── JIRA (issue tracking, agile boards, workflow customization)
      ├── Bugzilla (open source, advanced search, reporting)
      └── GitHub Issues (integrated with repos, labels, PR linking)
```
 
# Testing Tools - Mind Map

```
Testing Tools
├── JMeter Apache
│   ├── Definition
│   │   ├── Open source load testing tool
│   │   ├── Java-based application
│   │   └── Apache Software Foundation
│   ├── Features
│   │   ├── Protocol support
│   │   │   ├── HTTP HTTPS
│   │   │   ├── FTP
│   │   │   ├── SOAP REST
│   │   │   ├── Database JDBC
│   │   │   ├── LDAP
│   │   │   ├── SMTP POP3
│   │   │   └── TCP
│   │   └── Test plan components
│   │       ├── Thread groups
│   │       ├── Samplers
│   │       ├── Listeners
│   │       ├── Assertions
│   │       ├── Timers
│   │       └── Configuration elements
│   ├── Test Plan Structure
│   │   ├── Thread Group
│   │   │   ├── Number of threads
│   │   │   ├── Ramp-up period
│   │   │   ├── Loop count
│   │   │   └── Scheduler
│   │   ├── HTTP Request
│   │   │   ├── Server name
│   │   │   ├── Port
│   │   │   ├── Method
│   │   │   ├── Path
│   │   │   └── Parameters
│   │   ├── Response Assertions
│   │   │   ├── Pattern matching
│   │   │   ├── Response code
│   │   │   └── Response message
│   │   └── Listeners
│   │       ├── View Results Tree
│   │       ├── Summary Report
│   │       ├── Aggregate Report
│   │       └── Graph Results
│   ├── Load Testing
│   │   ├── Performance testing
│   │   ├── Stress testing
│   │   ├── Endurance testing
│   │   ├── Spike testing
│   │   └── Scalability testing
│   ├── Benefits
│   │   ├── Open source
│   │   ├── GUI and command line
│   │   ├── Extensible via plugins
│   │   ├── Cross-platform
│   │   └── Large community
│   └── Limitations
│       ├── Resource intensive
│       ├── Not for browser simulation
│       └── JavaScript heavy apps
├── Load Testing
│   ├── Definition
│   │   ├── Test system under expected load
│   │   ├── Verify performance requirements
│   │   └── Identify bottlenecks
│   ├── Types of Load Tests
│   │   ├── Load testing
│   │   │   ├── Expected concurrent users
│   │   │   └── Normal traffic patterns
│   │   ├── Stress testing
│   │   │   ├── Beyond normal capacity
│   │   │   └── Breaking point
│   │   ├── Endurance testing
│   │   │   ├── Extended duration
│   │   │   └── Memory leaks
│   │   ├── Spike testing
│   │   │   ├── Sudden load increase
│   │   │   └── Recovery behavior
│   │   └── Scalability testing
│   │       ├── Capacity planning
│   │       └── Growth projection
│   ├── Load Testing Process
│   │   ├── Define test scenarios
│   │   ├── Create test scripts
│   │   ├── Configure load profile
│   │   ├── Execute tests
│   │   ├── Analyze results
│   │   └── Optimize and retest
│   └── Key Metrics
│       ├── Response time
│       │   ├── Average
│       │   ├── Median
│       │   └── 90th 95th 99th percentile
│       ├── Throughput
│       │   ├── Requests per second
│       │   └── Transactions per second
│       ├── Error rate
│       │   ├── Failed requests
│       │   └── Error percentage
│       ├── Resource utilization
│       │   ├── CPU usage
│       │   ├── Memory usage
│       │   ├── Network I/O
│       │   └── Disk I/O
│       └── Concurrency
│           ├── Simultaneous users
│           └── Active connections
├── Other Testing Tools
│   ├── Selenium
│   │   ├── Browser automation
│   │   ├── Web application testing
│   │   ├── Cross-browser support
│   │   └── WebDriver API
│   ├── JUnit
│   │   ├── Unit testing framework
│   │   ├── Java applications
│   │   ├── Test annotations
│   │   └── Assertions
│   ├── TestNG
│   │   ├── Advanced testing framework
│   │   ├── Annotations
│   │   ├── Data-driven tests
│   │   └── Parallel execution
│   ├── Postman
│   │   ├── API testing
│   │   ├── REST API testing
│   │   ├── Collections
│   │   └── Environment variables
│   ├── Cypress
│   │   ├── Modern web testing
│   │   ├── End-to-end testing
│   │   ├── Time travel debugging
│   │   └── Real-time reloading
│   └── Appium
│       ├── Mobile application testing
│       ├── iOS and Android
│       ├── Cross-platform
│       └── WebDriver protocol
├── Test Automation Frameworks
│   ├── Types
│   │   ├── Linear scripting
│   │   ├── Modular testing
│   │   ├── Data-driven testing
│   │   ├── Keyword-driven testing
│   │   └── Hybrid framework
│   ├── Components
│   │   ├── Test script library
│   │   ├── Object repository
│   │   ├── Test data
│   │   ├── Reporting module
│   │   └── Configuration management
│   ├── Benefits
│   │   ├── Repeatability
│   │   ├── Speed
│   │   ├── Consistency
│   │   ├── Early detection
│   │   └── Cost effective long term
│   └── Challenges
│       ├── Initial investment
│       ├── Maintenance overhead
│       ├── Technical expertise
│       └── Tool selection
├── Performance Testing Tools
│   ├── LoadRunner
│   │   ├── Enterprise performance testing
│   │   ├── Virtual users
│   │   ├── Protocol support
│   │   └── Analysis reports
│   ├── Gatling
│   │   ├── Load testing tool
│   │   ├── Scala-based
│   │   ├── High performance
│   │   └── Code-based tests
│   ├── Locust
│   │   ├── Python-based
│   │   ├── Distributed testing
│   │   ├── Write tests in code
│   │   └── Scalable
│   └── k6
│       ├── Modern load testing
│       ├── JavaScript scripts
│       ├── Developer focused
│       └── Cloud integration
├── Test Management Tools
│   ├── TestRail
│   │   ├── Test case management
│   │   ├── Test planning
│   │   ├── Test execution
│   │   └── Reporting
│   ├── Zephyr
│   │   ├── JIRA integration
│   │   ├── Test management
│   │   ├── Test cycles
│   │   └── Dashboards
│   └── qTest
│       ├── Enterprise test management
│       ├── Requirements traceability
│       └── Test automation integration
├── Static Analysis Tools
│   ├── SonarQube
│   │   ├── Code quality analysis
│   │   ├── Security scanning
│   │   ├── Code smells
│   │   └── Technical debt
│   ├── ESLint
│   │   ├── JavaScript linting
│   │   ├── Code standards
│   │   └── Automated fixes
│   └── PMD
│       ├── Source code analyzer
│       ├── Bug detection
│       └── Code standards
└── Bug Tracking Tools
    ├── JIRA
    │   ├── Issue tracking
    │   ├── Project management
    │   ├── Agile boards
    │   └── Workflow customization
    ├── Bugzilla
    │   ├── Bug tracking system
    │   ├── Open source
    │   ├── Advanced search
    │   └── Reporting
    └── GitHub Issues
        ├── Integrated with repositories
        ├── Labels and milestones
        └── Pull request linking
```
