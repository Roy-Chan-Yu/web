## Servlet Container

- The servlet container is `the part of web server` which can be run in `a separate process`. We can classify the servlet container states in three types:

1. Standalone

> It's typical Java-based servers in which `the servlet container` and the `web servers` are the `integral part of a single program` i.e.Tomcat running by itself.

2. In-process

> It's separated from the web server,because a different program runs within the address space of the main server as a plug-in.(外掛) i.e. Tomcat running inside the JBoss.

3. Out-of-Process

> The web server and servlet container are `different programs` which are run uf a different process.<br>
> For performing the communicattions between them, web server uses the plug-in provided by the servlet container.

## Servlet Container performs many operation below

- Life Cycle Management
- Multithreaded support
- Object Pooling
- Security etc...

### Object Pooling

> 如果有某個物體需要經常實例化並進行銷毀
>這會導致實例化的成本過高
>這時候就可以透過物件池來對物體進行管理
>D.pattern Singleton(單例模式)
