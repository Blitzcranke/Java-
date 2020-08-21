### 包装类与基本类型 拆箱装箱
> Interface继承自Object, 属于引用数据类型, 可以进行向上转型操作


**equals和==**

equals判断值相等, ==判断是否为同一对象
```java
    import java.util.Scanner;
    public class Test01 {
        // 验证用户名和密码
        public static boolean validateLogin(String uname, String upwd) {
            boolean con = false;
            if (uname.equals("admin") && upwd.equals("admin")) { // 比较两个 String 对象
                con = true;
            } else {
                con = false;
            }
            return con;
        }
        public static void main(String[] args) {
            Scanner input = new Scanner(System.in);
            System.out.println("------欢迎使用大数据管理平台------");
            System.out.println("用户名：");
            String username = input.next(); // 获取用户输入的用户名
            System.out.println("密码：");
            String pwd = input.next(); // 获取用户输入的密码
            boolean con = validateLogin(username, pwd);
            if (con) {
                System.out.println("登录成功！");
            } else {
                System.out.println("用户名或密码有误！");
            }
        }
    }
```
***

**向上造型和向下造型**
```java
/*
	向上造型：父类引用指向子类对象（子类型，实例也是子类的实例化）；
    向下造型：子类引用指向父类对象（父类型，实例是子类的实例化）；
	 */
class A {
}

class B extends A {
}

A a = new A();
B b = new B();

A a1 = b;// 向上造型
B b1 = (B) a1; // 向下造型
B b2 = a; // ClassCastException,a的类型是A,实例化也是A
```
***