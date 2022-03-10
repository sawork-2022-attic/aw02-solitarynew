# POS in Shell

##对于分层系统的理解
为了应对程序不断的变化，分层架构是一种行之有效的方式，通过分层隔离不同的关注点，降低不同层级之间的耦合度，从而应对软件系统不断变化的要求。

经典的分层架构：用户界面层，业务逻辑层，数据访问层。隔离除了不同的关注点，用户界面层只关注用户面对的界面，不关注数据的来源与内容；业务逻辑层只关注将什么内容与格式的数据返回给用户界面层，而不关注数据的来源；数据访问层只关注从何种来源获取与操作数据，而不关注如何处理与显示数据。
这样进行分层很好的隔离了不同的层级，对于需求的改变，往往只需要对每一层单独的修改即可，极大的降低了不同层之间的耦合度。

正如本项目中的Pos Shell，用户界面层即为cli包内的类，业务逻辑层即为biz
包里的类，数据访问层即为db包里的类。cli只与biz联系，biz与上层的cli，下层的db联系，db只与上层的biz联系。
db只关注数据来源，biz只关注业务逻辑，cli只关注用户逻辑，做到了分层隔离。

The demo shows a simple POS system with command line interface. Currently it implements three commands which you can see using the `help` command.

```shell
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.5.7)
 
shell:>help
AVAILABLE COMMANDS

Built-In Commands
        clear: Clear the shell screen.
        exit, quit: Exit the shell.
        help: Display help about available commands.
        history: Display or save the history of previously run commands
        script: Read and execute commands from a file.
        stacktrace: Display the full stacktrace of the last error.

Pos Command
        a: Add a Product to Cart
        n: New Cart
        p: List Products
```

Everytime a customer come to make a purchase, use `n` to create a new cart and then use `a ${productid} ${amount}` to add a product to the cart.

Please make the POS system robust and fully functional by implementing more commands, for instance, print/empty/modify cart.

Implementing a PosDB with real database is very much welcome. 

Please elaborate your understanding in layered systems via this homework in your README.md.
