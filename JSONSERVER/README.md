##接口规范： 

1. 获取所有用户信息
http://localhost:3000/users
1. 获取所有公司信息
http://localhost:3000/companies
1. 获取id为1的用户信息
http://localhost:3000/users/1
1. 获取id为1的公司信息
http://localhost:3000/companies/1
1. 获取所有id为3的公司的用户
http://localhost:3000/companies/3/users
1. 根据公司名字获取信息
http://localhost:3000/companies?name=Microsoft
1. 根据多个名字获取公司信息
http://localhost:3000/companies?name=Microsoft&name=Apple
1. 获取一页中只有两条的数据
http://localhost:3000/companies?_page=1&_limit=2
1. 升序排序（asc升序 desc降序）
http://localhost:3000/companies?_sort=name&_order=asc
1. 获取年龄30以上的用户数据
http://localhost:3000/users?age_gte=30
1. 获取年龄在30到40之间的用户数据
http://localhost:3000/users?age_gte=30&age_lte=40
1. 搜索用户信息
http://localhost:3000/users?q=e



 