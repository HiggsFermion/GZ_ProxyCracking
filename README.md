# GZ_ProxyCracking
## 东莞中学代理上网的一种解决方案

### 原理
通过`GitHub Action`自动访问代理上网的通过页面

### 实践
1. 创建一个项目
2. 在`Actions`中创建如下的工作流，保存为`.yml`文件
   1. 找到`Skip this and set up a workflow yourself`
   2. 复制下面的`yml`代码块，修改必要的部分
   **注意：这里的时间为协调世界时（UTC），请先将当前时区的时间转化为 UTC +0**
   
   可以在这里查看[时间差](https://time.is/UTC)
   
``` yml
name: Proxy

on:
  schedule:
    - cron: 'mm hh * * *'

# 在指定时间触发，如12:00表达为 '00 12 * * *'

jobs:
  visit_url:
    runs-on: ubuntu-latest
    steps:
      - name: Fetch URL
        run: |
          curl https://ding.dgzx.net/show/DingScanLoginHTML/gz?clientip=***

# clientip=后添加教室ip地址，通常是10.167.82.**

```
   3. 点击`Commit changes...`保存文件，一个`.yml`文件应该在`.github/workflows`下生成

*********

**你可以在Issues中提交问题**
**Star Our Project ⭐**
