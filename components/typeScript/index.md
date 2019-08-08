# TypeScript
## 基础类型     https://www.tslang.cn/docs/handbook/basic-types.html
### 1. boolean  
```
let isDone: boolean = false;
```

### 2. number
```
let decLiteral: number = 6;
let hexLiteral: number = 0xf00d;
let binaryLiteral: number = 0b1010;
let octalLiteral: number = 0o744;
```

### 3. string
```
let name: string = "bob";
name = "smith";
```

### 4. Null 和 Undefined
```
// Not much else we can assign to these variables!
let u: undefined = undefined;
let n: null = null;
```
默认情况下null和undefined是所有类型的子类型。 就是说你可以把 null和undefined赋值给number类型的变量。

### 5. Array
```
let list: number[] = [1, 2, 3];
let list: Array<number> = [1, 2, 3];
```

### 6. Object
```
declare function create(o: object | null): void;

create({ prop: 0 }); // OK
create(null); // OK

create(42); // Error
create("string"); // Error
create(false); // Error
create(undefined); // Error
```

### 7. 元组 Tuple
```
// Declare a tuple type
let x: [string, number];
// Initialize it
x = ['hello', 10]; // OK
// Initialize it incorrectly
x = [10, 'hello']; // Error

console.log(x[0].substr(1)); // OK
console.log(x[1].substr(1)); // Error, 'number' does not have 'substr'

x[3] = 'world'; // OK, 字符串可以赋值给(string | number)类型
console.log(x[5].toString()); // OK, 'string' 和 'number' 都有 toString
x[6] = true; // Error, 布尔不是(string | number)类型
```
### 8. 枚举
### 9. Any
### 10. Void
### 11. 类型断言
    有时候你会遇到这样的情况，你会比TypeScript更了解某个值的详细信息。 通常这会发生在你清楚地知道一个实体具有比它现有类型更确切的类型。
    通过类型断言这种方式可以告诉编译器，“相信我，我知道自己在干什么”。 类型断言好比其它语言里的类型转换，但是不进行特殊的数据检查和解构。 它没有运行时的影响，只是在编译阶段起作用。 TypeScript会假设你，程序员，已经进行了必须的检查
  + 类型断言有两种形式。 其一是“尖括号”语法
  ```
    let someValue: any = "this is a string";
    let strLength: number = (<string>someValue).length;
  ```
  + 另一个为as语法：
  ```
    let someValue: any = "this is a string";
    let strLength: number = (someValue as string).length;
  ```

### 12. Never


## 变量声明


## 接口
### 1. 属性检查
### 2. 可选属性
### 3. 只读属性
### 4. 额外的属性检查
### 5. 函数类型
### 6. 可索引的类型


## 类
### 1. 类
```
class Greeter {
    greeting: string;
    constructor(message: string) {
        this.greeting = message;
    }
    greet() {
        return "Hello, " + this.greeting;
    }
}

let greeter = new Greeter("world");
```

### 2. 继承

### 3. 公共，私有与受保护的修饰符
  + 默认为 public
  + private 
  + protected

### 4. 静态属性


## 函数
### 1. 给函数添加类型
```
function add(x: number, y: number): number {
    return x + y;
}
```