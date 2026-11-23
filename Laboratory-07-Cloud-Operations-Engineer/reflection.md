# Reflection

Checking the host server's resources matters even when the containers are running perfectly, because every container depends on the host underneath it. A container can be configured flawlessly and still fail if the physical machine runs out of RAM or disk space. It can never perform better than the hardware hosting it allows.

If a user complained that they could not log in, the `docker logs` command would show me the exact HTTP requests that reached the server around the time of the complaint. I could look for failed authentication attempts, 500-level server errors, or requests that never finished. These would point directly to whether the cause was on the client side, in the network, or in the application itself.

The difference between monitoring logs and monitoring metrics lies in what each one reveals. Logs (Checkpoint 4) are detailed, timestamped records of individual events, and they explain *why* something happened. Metrics (Checkpoint 5) are numerical measurements, such as CPU percentage and memory usage, sampled over time, and they show *that* something is happening right now. Metrics alert you that there is a problem, and logs let you investigate its cause.

Large enterprises that run thousands of containers depend on centralized tools instead of checking each one by hand. A tool like Prometheus collects metrics from every server and container at regular intervals and keeps them in a time-series database. Grafana then turns that data into dashboards that engineers can scan at a glance. This approach scales to entire fleets of machines in a way that running `docker stats` on one container at a time never could.

My ability to troubleshoot Linux environments has clearly improved since this lab. Rather than guessing at a problem from its symptoms alone, I now naturally turn to the real data. I check resource usage with `free`, `df`, and `top`, then compare it against container logs and live metrics before drawing any conclusions about what is actually wrong.
