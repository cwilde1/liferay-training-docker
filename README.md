# Liferay Training

### Start Docker Containers

Run the following command in the project root to start the Liferay and MySQL containers:

```
docker-compose up -d
```
After both containers have started, go to http://localhost:8080 to access liferay.
To deploy modules, copy them into the deploy folder,which is mapped to the %LIFERAY_HOME%/deploy folder.

### Access MySQL

To access the MySQL database running in Docker, use:

```
docker exec -it liferay2023q310-mysql mysql -u root -p
```

Default credentials are:
- User: root
- Password: root

## Browse files in the Container

Run this from a windows command prompt.
Once inside, you can manage files. 
```
docker exec -it liferay bash
```

## Liferay Gogo Shell Commands

Liferay includes the Gogo shell, a command-line tool for interacting with the OSGi runtime. You can access it from the Liferay server console or by connecting via telnet (default port 11311).

### Common Gogo Shell Commands

- `lb`  
  Lists all OSGi bundles and their states (Installed, Active, etc).

- `services`  
  Lists all registered OSGi services.

- `help`  
  Shows available commands and their usage.

- `scr:list`  
  Lists all OSGi Declarative Services components.

- `scr:info <component name>`  
  Shows details about a specific OSGi component.

- `log:get`  
  Displays recent log entries from the OSGi log service.

- `shutdown`  
  Shuts down the Liferay server.

### How to Access

- **From the Liferay console:**
  Just type the commands directly if you see the `g!` prompt.
- **Via telnet:**
  Connect using `telnet localhost 11311` and then enter commands at the `g!` prompt.

For more information, see the [Liferay Gogo Shell documentation](https://learn.liferay.com/dxp/latest/en/developing-applications/core-frameworks/gogo-shell.html).
