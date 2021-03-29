# 排班

> 项目文件夹为views/schedual，define、arrage 和 boardDetail 为公用页面，doctor 和 nurse 就是单独的。

> 步骤为在班次定义页面进行定义，方便在排班页面进行选择 > 在排班页面进行选择月份进行查看，无数据的周可以进行排班，有数据的周可以进行审核，为待审核状态，若审核不通过的周为审核不通过的状态可以进行重新排班 > 排班/排班审核页面进行审核/排班页面进行重新排班 

```flow
st=>start: 开始框
op1=>operation: 排班定义
op2=>operation: 排班
cond=>condition: 排班审核(通过或不通过?)
sub1=>subroutine: 审核不通过
io=>inputoutput: 排班页面查看(审核通过)
e=>end: 结束框
st->op1->op2->cond
cond(yes)->io->e
cond(no)->sub1(right)->op2
```

- 医生和护士的具体排班操作页面，通过父组件传入的 type 值进行区分，0是护士，1是医生。排班和重新排班通过 url 上的传值 reset 为 true 来区分。

