# What is this?

Arzu is a Gradle project template for bootstrapping true microservices using Docker images and Jlink to their maximum potential

# Why should I use it?
Well let's see:
- [OpenJDK 11](https://hub.docker.com/_/openjdk): 243 MB
- OpenJDK 11-Alpine: Tough luck, not official, google it
- [AdoptOpenJDK-JDK11-Alpine](https://hub.docker.com/r/adoptopenjdk/openjdk11): 200 for the JDK,down to 80ish for the JRE and they're getting to 50 in the nightlies
- This bad girl? [6 MB](https://github.com/alkoclick/alpine-jdk-nojdk)

I mean, if you wanna set up a _micro_ service, 200MB just doesn't sound very _micro_, does it? Especially when your entire codebase gets down to less than 100 KB of compiled code and uses like, 5 modules. Cmon JDK, you can do better!   

# tl;dr
- Requirements: A working JDK/JRE (crazy, right?)
- Uses [Badass Jlink plugin](https://github.com/beryx/badass-jlink-plugin/) to analyze the module dependencies your code has, then bundle them nicely in a portable JVM
- Bases off an [alpine image without a JDK](https://github.com/alkoclick/alpine-jdk-nojdk)
- Uses [Google JiB plugin](https://github.com/GoogleContainerTools/jib/) to pack that runnable in a docker image and sets the entrypoint to run it
- _Boom, done, now write awesome code_

# How do I use Arzu?
You can just copy the build.gradle magic sauce. You can also fork the project or download