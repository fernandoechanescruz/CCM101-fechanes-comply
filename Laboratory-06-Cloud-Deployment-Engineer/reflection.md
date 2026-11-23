# Reflection

Writing a docker-compose.yml file makes a cloud engineer's work much easier than typing commands by hand, because the whole application stack, including every container, environment variable, port, and dependency, is described in one readable file. There is no need to remember and retype a long docker run command for each container. You run a single command and Docker takes care of the rest. The file also doubles as documentation, and it can be version-controlled, shared, and reused across environments.

If a YAML file has an indentation mistake, such as a Tab used in place of spaces, it will typically fail to parse altogether. Docker Compose will report a syntax error and refuse to start any containers, because YAML depends on consistent indentation to determine which settings belong to which service. That is why careful, consistent spacing matters so much when editing Compose files manually.

Environment variables such as MYSQL_PASSWORD were used in the Compose file so that sensitive values are not hardcoded into the application itself. This makes credentials easier to manage and allows the same Docker image to be reused in different environments by changing only the variables. When the values are loaded from an external .env file, it also keeps secrets out of version control.

Getting a fully working enterprise cloud storage system running in only a few minutes was a real turning point in my understanding of what cloud engineers do day to day. Setting up a private alternative to Google Drive would normally be complex, yet the Compose file handled almost all of it, which showed me how much infrastructure-as-code hides behind a simple file.

Since Mission 1, my view of cloud computing has changed. I used to see it as "someone else's computer," and now I understand it as a discipline built on repeatable, automatable infrastructure. I have gone from provisioning a single VM, to managing storage, to orchestrating several linked containers as code instead of through manual steps.
