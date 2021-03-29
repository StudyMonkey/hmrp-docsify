# 医德医风

> 项目文件夹为views/medicalEthics。

> 基本步骤为在基础配置里面进行相关定义 > 考评方案页面配置考评方案 > 进行考评 ( 个人、科室、党支部、分管领导 )

```flow
st=>start: 开始框
op1=>operation: 考评等级(新增方案时配置等级)
op2=>operation: 党支部分管范围(党支部审核环节时，科室考评提交后，根据这个归到哪个部门下)
op3=>operation: 考评周期定义(根据配置的时间规定这段时间内才能进行考评)
op4=>operation: 考评方案(按步骤选基础项目，加减分项目，人员，等级进行配置考评方案)
op5=>operation: 个人自评(考评方案中被选到的人员会生成个人自评)
cond=>condition: 科室考评(通过或撤回?)
sub1=>subroutine: 撤回
cond2=>condition: 党支部环节(方案是否配置党支部考评环节)
sub2=>subroutine: 未配置党支部考评
cond3=>condition: 党支部考评(通过或撤回?)
sub3=>subroutine: 撤回
op7=>operation: 考评委员会考评
e=>end: 结束框
st->op1->op2->op3->op4->op5->cond->cond2->cond3->op7->e
cond(yes)->cond2(yes)->cond3
cond(no)->sub1(right)->op5
cond2(no)->sub2(right)->op7
cond3(no,left)->sub3(top)->cond
cond3(yes)->op7
```