# MyBlog_flask
- 数据库建模时遇到了一个问题：sqlalchemy.exc.InvalidRequestError: Table 'admin' is already defined for this MetaData instance.（py3才会出现的问题，默认已经有个实例，再次创建就会冲突，所以需要说明一下）

    解决方法：加上__table_args__ = {'extend_existing': True}
    
    https://stackoverflow.com/questions/27812250/sqlalchemy-inheritance-not-working
- 什么是setUp()和tearDown()函数?

　　
    setUp()函数是在众多函数或者说是在一个类里面最先被调用的函数，而且每执行完一个函数都要从setUp()调用开始后再执行下一个函数，有几个函数就调用他几次，与位置无关，随便放在那里都是他先被调用。

　　
    tearDown()函数是在众多函数执行完后他才被执行，意思就是不管这个类里面有多少函数，他总是最后一个被执行的，与位置无关，放在哪里都行，最后不管测试函数是否执行成功都执行tearDown()方法；如果setUp()方法失败，则认为这个测试项目失败，不会执行测试函数也不执行tearDown()方法。

- 为什么我们要用setUp()和tearDown()函数?

　　
   我们利用这一特性在自动化中setup主要是进行测试前的初始化工作，比如在接口测试前面做一些前置的参数赋值，数据库操作等等 teardown是测试后的清除工作，比如参数还原或销毁，数据库的还原恢复等
