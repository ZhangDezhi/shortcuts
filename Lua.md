
## 注释
```lua

-- 两个横向表示注释


--[[
 
 表示多行 注释

--]]
```

## 变量和流控制

```lua
num = 42 --所有对数字都是double
s   = 'walternate'--不可变字符串
t   = "双引号也可以"
u   = [[两个方括号
用于
多行字符串]]
t = nil --未定义对t;Lua支持垃圾回收
-- do/end 之类对关键字表示出程序块:
while num < 50 do
    num = num + 1 -- 没有++ 或者 + = 运算符
end

-- if语句
if num > 40 then
  print('over 40')
elseif s ~='walternate' the --~=表示不等于
-- == 表示等于;适用于字符串.
io.write('not over 40\n') -- 默认输出到stdout
else 
-- 默认变量都是全局变量
thisIsGlobal=5 -- 通常用驼峰命名

-- 如何定义局部变量
local line = io.read() -- 读取stdin的下一行

-- ..操作符用于连接字符串
print('Winter is coming,'..line)
end


-- 未定义对变量返回nil
-- 这不会出错
foo=anUnknownVariable --现在 foo= nil

aBoolValue=false
-- 只有nil 和 false 是false;0和''都是true

if not aBoolValue then print('twas false') end

-- 'or'和'and'都是课短路对.
-- 类似于C/js丽对a?b:c操作符 
ans = aBoolValue and 'yes' or 'no' --> 'no'

karlSum = 0
for i = 1,100 do -- 返回包括两端
  karlSum = karlSum + i
  end

  -- 使用 "100,1,-1" 表示递减对范围:
  fredSum = 0
  for j = 100,1,-1 do fredSum = fredSum + j end

  -- 通常,范围表达式为 begin ,end [,step]
  -- 另一种循环表达式
  repeat
    print("the way of the future")
	num = num - 1
until num == 0

```


## 函数


