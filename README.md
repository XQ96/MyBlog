# MyBlog_flask
- 数据库建模时遇到了一个问题：sqlalchemy.exc.InvalidRequestError: Table 'admin' is already defined for this MetaData instance.

    解决方法：加上__table_args__ = {'extend_existing': True}
    
    https://stackoverflow.com/questions/27812250/sqlalchemy-inheritance-not-working
