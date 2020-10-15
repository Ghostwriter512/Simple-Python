
```
#第一种方法，字典动态填充
D = {
        'name': {'firstname': 'Kobe', 'lastname': 'Bryant'},
        'job': {'writer', 'player'},
        'age': {24}
    }
print(D['name'])
print(D['name']['firstname'])
D['sex'] = 'gender'

#第二种方法，列表动态生成
key_list = ['a', 'b', 'c']
value_list = [111, 222, 333]
D2 = dict(zip(key_list, value_list))
print(D2)
print(D2.get('d',0)) #如果存在键值'd'，则返回'd'所对应的值，否则返回0，如果不写0.则返回None。

#第三种方法，用键值对元组组成的列表构造字典。
D3 = dict([('aa',11),('bb',22),('cc',33)])
print(D3.get('aa'))

D.update(D3)


print('abc' in D) #False 这是初级方法
#还有一种更高级的方法是用get()方法实现上述判断功能，get方法中第二个参数指的是键不存在时指定返回的默认值，如果不设置这个值，则返回None。

print(D['abc']) #KeyError: 'abc'

#应用场景
'''
#!/usr/bin/env python
# -*- coding: UTF-8 -*-
import sys
reload(sys)
sys.setdefaultencoding('utf-8')
import MySQLdb
import MySQLdb.cursors
 
db = MySQLdb.connect("192.168.101.234", "root", "luca321", "monworks",cursorclass=MySQLdb.cursors.DictCursor)
cursor = db.cursor()
cursor.execute("select id,name from test")
results = cursor.fetchall()
for row in results:
print row["id"]
'''


```
