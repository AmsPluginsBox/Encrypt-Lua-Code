# Encrypt-Lua-Code
Encrypt Lua Code, and call it through an AmsLuac dll

It is a great tool for LUA code protection,
Support, windows and lua5.1.4, not tested with other versions of LUA, but I believe it is possible to use it in other versions of LUA.

1 = Let's encrypt lua code with an executable: LuaEncrypt.exe was created in C++

2 = Let's call the encrypted lua code, to call this encrypted code we will use a DLL: AmsLuac.dll created in C++.

3 = Note, it is a tool that will encrypt only LUA code.

4 = As an example, we will use a function.

-------------------------------------------------- ---------------------------------------------

--- function

function TestLuaEncrypt()

--- LUA script

t = {"A","B","C"}

for t, j in pairs(t) do

p = j;

print(p);

end

return p;

end

-------------------------------------------------- ---------------------------------------------

5 = To encrypt this function use the executable "LuaEncrypt.exe"

6 = To call this function already encrypted use "AmsLuac.dll"

-------------------------------------------------- ---------------------------------------------

pcall(package.loadlib("AmsLuac.dll", "irPlg_Action_RegisterActions"));

AmsLuac.LoadFile("LuaEncrypt.cl"); ---- file

--- function;

TestLuaEncrypt();

-------------------------------------------------- ---------------------------------------------
