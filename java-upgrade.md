# Template for the Java 8-11 upgrade process.
_This is a template I created to help with a Java upgrade_

## Before starting - verify and check existing setup

### Note unit test status 
_Run unit tests, note any that are failing._

|Unit test|Details|
|---------|-------|
|         |       |

### Note deprecation warnings
_Use an eclipse filter to see deprecations warnings._

|Warning|
|-------|
|       |

### Compile and run
_Compile application successfully using maven._
_Run and smoke test_

|Notes|
|-----|
|     |

## Preparation

### Investigate Java 11 support of critical libraries.
_Read about the major libraries to determine upgrade requirements for Java 11 support.  Other libraries can be upgraded on an as-needs basis._

|Library|From version|To version|References|
|-------|------------|----------|----------|
|       |            |          |          |

### Check Application server
_For an application server, check the supported configurations.  Also, application servers sometimes provide a migration utility_

### Run jdeps over libraries
_The Jdeps tool can determine which libraries use internal methods that are deprecated in Java 11.  See https://developer.ibm.com/wasdev/blog/2016/11/02/a-first-look-at-liberty-on-java-9/ for good notes on jdeps._

```
jdeps.exe --jdk-internals --multi-release 11 *.jar
```

If the output contains:
* jdk.unsupported: the methods are available but unsupported (same as for Java 8). This is undesirable but acceptable.
* JDK removed internal API: the methods will no longer work.  These should be addressed by investigating/upgrading the library.

|Library|Notes|Resolution|
|-------|-----|----------|
|       |     |          |

## Compilation
* Resolve any compile-time errors in eclipse
* Investigate compile-time warnings in eclipse.  Resolve any introduced deprecations.  
* Run the maven build successfully.

|Code Unit|Change|
|---------|------|
|         |      |

## Runtime
* Execute the unit tests
* Start the application server and review log files for errors and warnings.
* Smoke test using a local environment

|Notes|Resolution|
|-----|----------|
|     |          |

## Enhancement Notes
* JVM tuning
* New java language features that may be useful

|Notes|
|-----|
|     |
