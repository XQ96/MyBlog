# MyBlog_flask
- 数据库建模时遇到了一个问题：sqlalchemy.exc.InvalidRequestError: Table 'admin' is already defined for this MetaData instance.（py3才会出现的问题，默认已经有个实例，再次创建就会冲突，所以需要说明一下）

    解决方法：加上__table_args__ = {'extend_existing': True}
    
    https://stackoverflow.com/questions/27812250/sqlalchemy-inheritance-not-working
