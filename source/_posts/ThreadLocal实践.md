---
title: ThreaLocal实践
tags:
  - 参考
---

### 例子

```java
public class UserHolder {
    private static final ThreadLocal<UserDTO> tl = new ThreadLocal<>();

    public static void saveUser(UserDTO user){
        tl.set(user);
    }

    public static UserDTO getUser(){
        return tl.get();
    }

    public static void removeUser(){
        tl.remove();
    }
}

```

将ThreadLocal封装到UserHolder类中写语法糖（保存获取移除等方法），实现松耦合。
