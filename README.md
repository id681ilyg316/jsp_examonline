## 本项目实现的最终作用是基于JSP在线考试管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 成绩管理
 - 登录页面
 - 管理员首页
 - 考生信息管理
 - 考生录入
 - 试卷管理
 - 题库管理
 - 题目录入
### 第2个角色为学生角色，实现了如下功能：
 - 学生主页
 - 学生登录
 - 开始考试
 - 查看成绩
## 数据库设计如下：
# 数据库设计文档

**数据库名：** examonline

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [paper](#paper) |  |
| [question](#question) |  |
| [score](#score) |  |
| [student](#student) | 学生表 |
| [teacher](#teacher) | 用户表 |

**表名：** <a id="paper">paper</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 试卷号  |
|  2   | time |   int   | 10 |   0    |    Y     |  N   |   NULL    | 考试时间  |
|  3   | qty_sing |   int   | 10 |   0    |    Y     |  N   |   NULL    | 单选题数量  |
|  4   | qty_muti |   int   | 10 |   0    |    Y     |  N   |   NULL    | 多选题数量  |
|  5   | qty_jud |   int   | 10 |   0    |    Y     |  N   |   NULL    | 判断题数量  |
|  6   | qty_fill |   int   | 10 |   0    |    Y     |  N   |   NULL    | 填空题数量  |
|  7   | qty_ess |   int   | 10 |   0    |    Y     |  N   |   NULL    | 简答题数量  |
|  8   | quantity |   int   | 10 |   0    |    Y     |  N   |   NULL    | 总题目数量  |

**表名：** <a id="question">question</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | number |   varchar   | 8 |   0    |    N     |  Y   |       | 题目序号  |
|  2   | type |   varchar   | 255 |   0    |    N     |  N   |       | 题目类型  |
|  3   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 题目标题  |
|  4   | select |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 题目选项  |
|  5   | score |   float   | 13 |   0    |    N     |  N   |       | 题目分值  |
|  6   | key |   varchar   | 255 |   0    |    N     |  N   |       | 题目答案/关键词  |
|  7   | img |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 题目配图  |

**表名：** <a id="score">score</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   varchar   | 16 |   0    |    N     |  Y   |       | 学生号  |
|  2   | score |   float   | 13 |   0    |    Y     |  N   |   -1    | 总分数  |
|  3   | score_sing |   float   | 13 |   0    |    Y     |  N   |   -1    | 单选题分数  |
|  4   | score_muti |   float   | 13 |   0    |    Y     |  N   |   -1    | 多选题分数  |
|  5   | score_jud |   float   | 13 |   0    |    Y     |  N   |   -1    | 判断题分数  |
|  6   | score_fill |   float   | 13 |   0    |    Y     |  N   |   -1    | 填空题分数  |
|  7   | score_ess |   float   | 13 |   0    |    Y     |  N   |   -1    | 简答题分数  |
|  8   | grade |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 成绩评价  |

**表名：** <a id="student">student</a>

**说明：** 学生表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   varchar   | 16 |   0    |    N     |  Y   |       | 学生号  |
|  2   | password |   varchar   | 16 |   0    |    Y     |  N   |   NULL    | 学生密码  |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 学生姓名  |
|  4   | class |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 学生班级  |
|  5   | score |   float   | 13 |   0    |    N     |  N   |   -1    | 学生成绩  |

**表名：** <a id="teacher">teacher</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   varchar   | 16 |   0    |    N     |  Y   |       | 教职工号  |
|  2   | password |   varchar   | 16 |   0    |    Y     |  N   |   NULL    | 教师密码  |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 教师姓名  |
|  4   | class |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 教师班级  |
|  5   | job |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 教师职称  |

**运行不出来可以微信 javape 我的公众号：源码码头**
