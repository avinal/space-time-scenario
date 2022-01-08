# Troubleshooting

- Make sure that all required ports (default 9080/9443/2379) are not used by other systems or processes.

  The following are commands to terminate a process that is listening on a specific port (on unix-based systems).

  ```bash
      sudo fuser -k 9443/tcp
  ```

- If the Docker container keeps restarting or failing, log in to the container and observe the logs to diagnose the problem.
  ```bash
  docker logs -f --tail container_id
  ```
