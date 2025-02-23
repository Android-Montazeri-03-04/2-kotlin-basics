# **جزوه درسی کاتلین – جلسه دوم** 🚀

## **مقدمه**

در این جلسه، مفاهیم پیشرفته‌تری از کاتلین را بررسی خواهیم کرد. مباحث امروز شامل **آرایه‌ها، لیست‌ها، برنامه‌نویسی تابعی (Functional Programming)، مدیریت مقدار `null` (Null Safety)، شی‌گرایی (Object-Oriented Programming)، و اینترفیس (Interface)** خواهد بود. هر بخش شامل تعریف، مثال‌های کاربردی، و تمرین‌های متنوع است.

---

# **۱. آرایه‌ها و لیست‌ها در کاتلین** 📦

## **تعریف آرایه و لیست**

✅ **آرایه (Array):**
- مجموعه‌ای از مقادیر با اندازه‌ی ثابت که بعد از مقداردهی اولیه تغییر نمی‌کند.
- همه‌ی عناصر آرایه باید از یک نوع داده‌ای باشند.
- سریع‌تر از لیست در دسترسی به عناصر است.

✅ **لیست (List):**
- مجموعه‌ای از مقادیر که اندازه‌ی آن می‌تواند تغییر کند.
- دو نوع اصلی دارد: **لیست غیرقابل تغییر (`listOf`)** و **لیست قابل تغییر (`mutableListOf`)**.
- قابلیت اضافه و حذف کردن آیتم‌ها را دارد.

## **مثال از آرایه‌ها**

```kotlin
val numbers = arrayOf(1, 2, 3, 4, 5)
println(numbers[0]) // دسترسی به اولین مقدار
numbers[2] = 10    // تغییر مقدار عنصر سوم
```

## **مثال از لیست‌ها**

```kotlin
val names = listOf("Ali", "Reza", "Sara") // لیست غیرقابل تغییر
val mutableNames = mutableListOf("Ali", "Reza") // لیست قابل تغییر
mutableNames.add("Sara")
```

## **تمرین‌ها**

✏️ **تمرین ۱:** برنامه‌ای بنویسید که یک لیست از اعداد دریافت کند و مجموع آن‌ها را محاسبه کند.

✏️ **تمرین ۲:** برنامه‌ای بنویسید که یک لیست از اعداد دریافت کند و بزرگ‌ترین مقدار را برگرداند.

### **پاسخ‌های پیشنهادی:**

```kotlin
fun main() {
    val numbers = listOf(1, 2, 3, 4, 5)
    val sum = numbers.sum()
    println("مجموع اعداد: $sum")
}
```

```kotlin
fun main() {
    val numbers = listOf(12, 45, 2, 78, 33)
    val maxNumber = numbers.maxOrNull()
    println("بزرگ‌ترین عدد: $maxNumber")
}
```

---

### تمرین چالشی باحال:
بازی حدس کلمه به صورت wordle در کاتلین
بله، حتماً! اینجا توضیحاتی در مورد مراحل کار و الگوریتم بازی به زبان فارسی برای دانش‌آموزان نوشته‌ام تا بتوانند از آن استفاده کنند و راحت‌تر مفهوم بازی را درک کنند.

---

### **توضیح بازی حدس کلمه با تعداد حدس محدود:**

**مراحل انجام بازی:**

1. **انتخاب کلمه:** ابتدا یک کلمه به‌طور تصادفی از لیستی از کلمات انتخاب می‌شود.
2. **مخفی کردن کلمه:** کلمه انتخابی مخفی می‌شود و به‌جای هر حرف یک نماد "_" قرار می‌گیرد. برای مثال، اگر کلمه "کتاب" باشد، کلمه به صورت " _ _ _ _ _ " نمایش داده می‌شود.
3. **تعداد حدس‌ها:** بازیکن برای حدس زدن کلمه تعداد معینی حدس دارد (در این بازی، 5 حدس مجاز است).
4. **ورود حدس‌ها:** بازیکن یک حرف را وارد می‌کند. سیستم بررسی می‌کند که آیا این حرف در کلمه موجود است یا نه.
   - اگر حرف وارد شده درست باشد، در جای خود در کلمه نمایش داده می‌شود.
   - اگر حرف اشتباه باشد، تعداد حدس‌های مجاز کاهش می‌یابد.
5. **نمایش کلمه مخفی:** پس از هر حدس، کلمه مخفی به‌روزرسانی می‌شود و کاربر می‌تواند وضعیت کلمه را مشاهده کند.
6. **اتمام بازی:** بازی زمانی تمام می‌شود که یکی از شرایط زیر رخ دهد:
   - **حدس صحیح:** بازیکن تمامی حروف کلمه را حدس زده باشد.
   - **تمام شدن حدس‌ها:** تعداد حدس‌های مجاز تمام شود.

**الگوریتم بازی:**

1. **انتخاب کلمه تصادفی** از لیست کلمات.
2. ایجاد یک رشته مخفی از همان طول کلمه انتخابی با نمادهای "_".
3. تعیین تعداد حدس‌های مجاز (در اینجا 10).
4. در هر دور از بازی:
   - از کاربر خواسته می‌شود یک حرف وارد کند.
   - بررسی می‌شود که آیا حرف وارد شده در کلمه وجود دارد یا نه.
   - اگر درست باشد، حرف در موقعیت صحیح نمایش داده می‌شود.
   - اگر اشتباه باشد، تعداد حدس‌ها کاهش می‌یابد.
5. پس از هر حدس، وضعیت کلمه و تعداد حدس‌های باقی‌مانده نمایش داده می‌شود.
6. بازی ادامه می‌یابد تا زمانی که:
   - کلمه کامل حدس زده شود.
   - یا تعداد حدس‌های مجاز تمام شود.
7. در پایان بازی، اگر کلمه حدس زده شده باشد، پیام تبریک نمایش داده می‌شود و در غیر این صورت، کلمه درست نمایش داده می‌شود.

---

### **مثال:**

فرض کنید کلمه انتخابی "کتاب" است و بازیکن 5 حدس دارد.

1. کلمه مخفی به صورت "_ _ _ _ " نمایش داده می‌شود.
2. بازیکن حرف "ک" را وارد می‌کند:
   - چون "ک" در کلمه هست، کلمه به " ک _ _ _ " تغییر می‌کند.
3. بازیکن حرف "م" را وارد می‌کند:
   - چون "م" در کلمه نیست، تعداد حدس‌های باقی‌مانده به 4 کاهش می‌یابد.
4. بازیکن حرف "ت" را وارد می‌کند:
   - چون "ت" در کلمه هست، کلمه به "ک ت _ _ _ " تغییر می‌کند.
5. بازی ادامه پیدا می‌کند تا زمانی که یا بازیکن کلمه را به‌طور کامل حدس بزند یا تعداد حدس‌هایش تمام شود.

```kotlin
fun main() {
    val words = listOf("کتاب", "پیشرفت", "اندروید", "برنامه")
    val randomWord = words.random()  // انتخاب کلمه تصادفی
    val hiddenWord = mutableListOf<Char>()
    randomWord.forEach {
        hiddenWord.add('_')
    }


    val maxGuesses = 10  // تعداد حدس‌های مجاز
    var remainingGuesses = maxGuesses

    println("بازی حدس کلمه شروع شد!")
    println("کلمه مخفی:")
    hiddenWord.forEach {
        print("_ ")
    }
    println()
    println("تعداد حدس‌های مجاز: $remainingGuesses")

    while (hiddenWord.contains('_') && remainingGuesses > 0) {
        print("یک حرف وارد کنید: ")
        val guess = readln().first()

        if (randomWord.contains(guess)) {

            for (i in 0..randomWord.length - 1) {
                if (randomWord[i] == guess) {
                    hiddenWord[i] = guess
                }
            }
            println("حرف صحیح!")
        } else {
            remainingGuesses--  // تعداد حدس‌های باقی‌مانده کم می‌شود
            println("حرف اشتباه! تعداد حدس‌های باقی‌مانده: $remainingGuesses")
        }

        println("کلمه مخفی: $hiddenWord")
    }

    if (remainingGuesses == 0) {
        println("\nشما متاسفانه نتواستید کلمه را حدس بزنید. کلمه درست: $randomWord")
    } else {
        println("\nتبریک می‌گویم! شما کلمه را حدس زدید: ${randomWord}")
    }
}
```

---


## ۲. جزوه توابع در کاتلین

### 1. مقدمه
توابع (Functions) در برنامه‌نویسی برای انجام یک سری عملیات خاص طراحی می‌شوند. کاتلین، زبان برنامه‌نویسی مدرن برای پلتفرم‌های مختلف، از توابع به عنوان یکی از مفاهیم اصلی استفاده می‌کند. توابع می‌توانند به شما کمک کنند تا کد خود را مرتب و قابل استفاده مجدد بنویسید.

در این جزوه، شما با انواع توابع در کاتلین آشنا خواهید شد و نحوه تعریف و استفاده از آن‌ها را یاد خواهید گرفت. همچنین مفاهیمی مثل **Higher-Order Functions** و **Lambda Expressions** که جزو ویژگی‌های قدرتمند کاتلین هستند، به طور مفصل توضیح داده می‌شود.

---

### 2. تعریف تابع در کاتلین
در کاتلین، برای تعریف یک تابع از کلمه کلیدی `fun` استفاده می‌شود. پس از آن نام تابع، نوع پارامترها و نوع نتیجه بازگشتی تابع را مشخص می‌کنیم.

#### ساختار تابع:
```kotlin
fun functionName(parameter: Type): ReturnType {
    // بدنه تابع
}
```

#### مثال ساده:
```kotlin
fun greet(name: String): String {
    return "Hello, $name"
}

println(greet("Alice"))  // خروجی: Hello, Alice
```

در این مثال، تابع `greet` یک پارامتر از نوع `String` به نام `name` دریافت می‌کند و یک مقدار از نوع `String` که همان عبارت "Hello" به همراه نام است، باز می‌گرداند.

---

### 3. توابع بدون مقدار بازگشتی (Void)
گاهی اوقات نیاز داریم که تابع هیچ مقداری را بازنگرداند. در این موارد، نوع بازگشتی تابع را `Unit` می‌گذاریم که معادل `void` در زبان‌های دیگر است.

#### مثال:
```kotlin
fun greet(name: String) {
    println("Hello, $name")
}

greet("Bob")  // خروجی: Hello, Bob
```

در این مثال، تابع `greet` هیچ مقداری بازنمی‌گرداند و فقط عبارت "Hello, Bob" را چاپ می‌کند.

---

### 4. توابع با پارامترهای پیش‌فرض (Default Parameters)
در کاتلین می‌توانیم برای پارامترهای تابع مقدار پیش‌فرض تعریف کنیم. این یعنی اگر هنگام فراخوانی تابع، مقداری برای یک پارامتر ارسال نشود، مقدار پیش‌فرض آن استفاده خواهد شد.

#### مثال:
```kotlin
fun greet(name: String = "Guest") {
    println("Hello, $name")
}

greet()  // خروجی: Hello, Guest
greet("Alice")  // خروجی: Hello, Alice
```

در اینجا اگر پارامتر `name` هنگام فراخوانی تابع ارسال نشود، مقدار پیش‌فرض "Guest" استفاده می‌شود.

---

### 5. توابع با تعداد پارامتر متغیر (Varargs)
اگر می‌خواهید تابعی بنویسید که تعداد پارامترهای متغیری بپذیرد، از `vararg` استفاده می‌کنید.

#### مثال:
```kotlin
fun sum(vararg numbers: Int): Int {
    return numbers.sum()
}

println(sum(1, 2, 3))  // خروجی: 6
println(sum(5, 10))  // خروجی: 15
```

در اینجا تابع `sum` هر تعداد عدد صحیح را که به آن داده شود جمع می‌کند. با استفاده از `vararg`، پارامتر `numbers` می‌تواند هر تعداد عدد را دریافت کند.

---

### 6. توابع با مقدار بازگشتی
گاهی اوقات تابع باید مقداری را بازگرداند. این مقدار می‌تواند هر نوعی باشد، مانند عدد، رشته، لیست و غیره.

#### مثال:
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

println(add(5, 3))  // خروجی: 8
```

در اینجا تابع `add` دو عدد صحیح دریافت کرده و مجموع آن‌ها را باز می‌گرداند.

---

### 7. Higher-Order Functions (توابع مرتبه بالاتر)
توابع مرتبه بالاتر (Higher-Order Functions) توابعی هستند که می‌توانند:
1. توابع دیگر را به عنوان پارامتر دریافت کنند.
2. توابعی را بازگردانند.

در کاتلین، توابعی که توابع دیگر را به عنوان ورودی می‌پذیرند یا توابعی را به عنوان خروجی بازمی‌گردانند، توابع مرتبه بالاتر نامیده می‌شوند. این ویژگی برای نوشتن کدهایی که انعطاف‌پذیری بیشتری دارند بسیار مفید است.

#### مثال 1: تابعی که تابعی را به عنوان ورودی می‌پذیرد
```kotlin
fun printResult(operation: (Int, Int) -> Int) {
    val result = operation(5, 3)
    println("Result is: $result")
}

fun add(a: Int, b: Int): Int = a + b
fun multiply(a: Int, b: Int): Int = a * b

printResult(::add)  // خروجی: Result is: 8
printResult(::multiply)  // خروجی: Result is: 15
```

در اینجا، تابع `printResult` یک تابع دیگر به نام `operation` می‌گیرد که دو عدد صحیح را می‌پذیرد و یک عدد صحیح باز می‌گرداند. سپس این تابع را روی مقادیر `5` و `3` فراخوانی می‌کند.

#### مثال 2: شبیه سازی درخواست سرور
```kotlin
fun fetchUserData(
    userId: Int,
    onSuccess: (String) -> Unit,
    onError: (String) -> Unit
) {
    // Simulating an API request (this would normally be an actual network call)
    val isSuccess = userId % 2 == 0  // Simulating success for even user IDs

    if (isSuccess) {
        onSuccess("User data for ID $userId")
    } else {
        onError("Error: User not found")
    }
}

fun main() {
    val userId = 3

    fetchUserData(
        userId,
        onSuccess = { data -> println("Success: $data") },
        onError = { error -> println(error) }
    )
}
```

در اینجا، تابع `getMultiplier` یک تابع جدید بازمی‌گرداند که یک عدد را با فاکتور مشخص شده ضرب می‌کند.

---

### 8. لامبدا (Lambda Expressions)
لامبدا (یا لامبدا اکسپرشن) به شما این امکان را می‌دهد که توابعی را به صورت ناشناس (بدون نیاز به تعریف نام تابع) تعریف کنید. لامبدا در کاتلین معمولاً برای استفاده در توابع مرتبه بالاتر و در جاهایی که به یک تابع نیاز داریم، اما نمی‌خواهیم تابع جدیدی تعریف کنیم، استفاده می‌شود.

#### ساختار لامبدا:
```kotlin
val lambdaName: (parameterType) -> returnType = { parameter -> expression }
```

#### مثال:
```kotlin
val sum = { a: Int, b: Int -> a + b }

println(sum(5, 3))  // خروجی: 8
```

در اینجا، یک لامبدا به نام `sum` تعریف کرده‌ایم که دو پارامتر می‌گیرد و مجموع آن‌ها را باز می‌گرداند.

#### استفاده از لامبدا در توابع مرتبه بالا:
```kotlin
fun performOperation(a: Int, b: Int, operation: (Int, Int) -> Int) {
    val result = operation(a, b)
    println("The result is: $result")
}

performOperation(5, 3, { x, y -> x * y })  // خروجی: The result is: 15
```

در اینجا از لامبدا برای تعریف عملیاتی که به تابع `performOperation` ارسال می‌شود استفاده کرده‌ایم.

---

### 9. `let` در کاتلین
در کاتلین، `let` یکی از ویژگی‌های مفید برای کار با متغیرهای غیر `null` است. `let` معمولاً به شما این امکان را می‌دهد که روی یک شیء عملیاتی انجام دهید، فقط اگر آن شیء `null` نباشد.

#### مثال:
```kotlin
val name = "Alice"

name?.let {
    println("The name is $it")
}  // خروجی: The name is Alice
```

در اینجا، از `let` برای دسترسی به مقدار `name` و انجام عملیاتی روی آن استفاده کرده‌ایم. اگر `name` برابر با `null` بود، هیچ عملی انجام نمی‌شد.

#### استفاده از `let` با `null safety`:
```kotlin
val name: String? = null

name?.let {
    println("The name is $it")
} ?: run {
    println("Name is null")
}
```

در اینجا، چون `name` برابر با `null` است، هیچ عملی داخل بلاک `let` اجرا نمی‌شود و به دستور `run` می‌رود که پیامی مبنی بر `null` بودن چاپ می‌کند.

---

### 10. Null Safety در کاتلین

کاتلین به طور پیش‌فرض اجازه نمی‌دهد که متغیرها مقدار `null` بگیرند. اما در صورتی که بخواهید یک متغیر `null` باشد، باید آن را به صراحت به عنوان قابل `null` تعریف کنید.

#### تعریف متغیر قابل `null`:
```kotlin
var name: String? = null  // متغیر name می‌تواند null باشد
```

#### استفاده از `?.` برای جلوگیری از ارور در `null`:
```kotlin
val length = name?.length  // اگر name null باشد، مقدار length برابر null خواهد بود
println(length)  // خروجی: null
```

#### استفاده از `?:` (Elvis Operator) برای مقدار پیش‌فرض در `null`:
```kotlin
val length = name?.length ?: 0  // اگر name null باشد، مقدار 0 باز می‌گردد
println(length)  // خروجی: 0
```

#### استفاده از `!!` برای فرض اینکه مقدار `null` نیست:
```kotlin
val length = name!!.length  // اگر name null باشد، یک NullPointerException ایجاد می‌شود
```

---

### 11. Extension Functions (توابع توسعه‌دهنده)
توابع توسعه‌دهنده یا **Extension Functions** این امکان را به شما می‌دهند که به کلاس‌های موجود توابع جدیدی اضافه کنید بدون اینکه نیاز به تغییر کد آن‌ها داشته باشید. این ویژگی در کاتلین بسیار مفید است و به شما این امکان را می‌دهد که به کلاس‌ها ویژگی‌های جدید بدهید.

#### تعریف Extension Function:
```kotlin
fun String.printWithStars() {
    println("*** $this ***")
}
```

در اینجا یک تابع توسعه‌دهنده به کلاس `String` اضافه کرده‌ایم که مقدار رشته

---
# **۳. اصول شی‌گرایی (Object-Oriented Programming) در کاتلین** 🏛️

✅ **تعریف:**
**برنامه‌نویسی شی‌گرا (OOP)** یک روش برنامه‌نویسی است که به جای رویه‌ها، از اشیا و کلاس‌ها برای طراحی سیستم استفاده می‌کند.

### **۱. کپسوله‌سازی (Encapsulation)**

```kotlin
class Person(private val name: String) {
    fun introduce() {
        println("سلام، من $name هستم.")
    }
}
```

### **۲. وراثت (Inheritance)**

```kotlin
open class Animal {
    fun makeSound() {
        println("حیوان صدا تولید می‌کند.")
    }
}

class Dog : Animal() {
    fun bark() {
        println("هاپ هاپ!")
    }
}
```

### **۳. چندریختی (Polymorphism)**

```kotlin
open class Shape {
    open fun draw() {
        println("در حال رسم یک شکل.")
    }
}

class Circle : Shape() {
    override fun draw() {
        println("در حال رسم یک دایره.")
    }
}
```

### **۴. انتزاع (Abstraction)**

```kotlin
abstract class Vehicle {
    abstract fun move()
}

class Car : Vehicle() {
    override fun move() {
        println("ماشین در حال حرکت است.")
    }
}
```

---

# **۴. اینترفیس (Interface) در کاتلین** 🎛️

✅ **تعریف:**
**اینترفیس (Interface)** مجموعه‌ای از متدها است که یک کلاس باید پیاده‌سازی کند.

### **مثال از اینترفیس:**

```kotlin
interface Drivable {
    fun drive()
}

class Car : Drivable {
    override fun drive() {
        println("ماشین در حال حرکت است.")
    }
}
```

✅ **مزایا:**
- امکان پیاده‌سازی چندین اینترفیس در یک کلاس.
- افزایش انعطاف‌پذیری در طراحی سیستم‌ها.

---


---
**جزوه: Data Class در Kotlin**

## مقدمه
در زبان برنامه‌نویسی Kotlin، یکی از انواع کلاس‌های پرکاربرد، **Data Class** است. این نوع کلاس‌ها برای نگهداری داده طراحی شده‌اند و به صورت خودکار قابلیت‌هایی مانند `equals()`، `hashCode()`، `toString()` و `copy()` را در اختیار برنامه‌نویس قرار می‌دهند.

## تعریف Data Class
در Kotlin، برای تعریف یک Data Class باید از کلمه‌ی کلیدی `data` در ابتدای تعریف کلاس استفاده کنیم.

### مثال ساده:
```kotlin
data class User(val name: String, val age: Int)
```

در این مثال، کلاسی به نام `User` تعریف شده است که دو ویژگی `name` و `age` دارد. با استفاده از `data`، برخی از توابع پرکاربرد به صورت خودکار ایجاد می‌شوند.

## ویژگی‌های Data Class
### ۱. تولید خودکار متد `toString()`

بدون نیاز به نوشتن دستی متد `toString()`، اطلاعات کلاس به صورت خوانا نمایش داده می‌شوند:
```kotlin
val user = User("Ali", 25)
println(user)  // خروجی: User(name=Ali, age=25)
```

### ۲. مقایسه اشیا با `equals()`
در Data Class، دو شیء برابر محسوب می‌شوند اگر مقادیر آن‌ها برابر باشد:
```kotlin
val user1 = User("Ali", 25)
val user2 = User("Ali", 25)
println(user1 == user2)  // خروجی: true
```

### ۳. متد `copy()` برای ایجاد نسخه جدید از شیء
data class به طور خودکار متدی به نام `copy()` دارد که امکان ایجاد یک نمونه جدید از شیء را فراهم می‌کند:
```kotlin
val user1 = User("Ali", 25)
val user2 = user1.copy(age = 30)
println(user2)  // خروجی: User(name=Ali, age=30)
```

## نکات مهم درباره Data Class
1. **حداقل یک ویژگی باید داشته باشند**
   ```kotlin
   data class Empty // خطا: کلاس داده‌ای حداقل یک ویژگی نیاز دارد
   ```
2. **ویژگی‌ها باید در primary constructor تعریف شوند**
   ```kotlin
   data class Person(var name: String) // صحیح
   class Person(var name: String) // کلاس معمولی
   ```
3. **کلاس نمی‌تواند `abstract`، `open`، `sealed` یا `inner` باشد**
   ```kotlin
   abstract data class Animal(val name: String) // خطا
   ```

## نتیجه‌گیری
Data Class در Kotlin یکی از ویژگی‌های قدرتمند است که کدنویسی را ساده‌تر و خواناتر می‌کند. این کلاس‌ها برای نگهداری داده‌ها استفاده می‌شوند و قابلیت‌های مفیدی مانند `copy()`، `toString()`، `equals()` و `hashCode()` را به صورت خودکار در اختیار برنامه‌نویس قرار می‌دهند. با درک صحیح این کلاس‌ها، می‌توانیم کدهای بهینه‌تر و خواناتری بنویسیم.

---

### **مدیریت لیست کاربران با `ArrayList`**  
در این مثال، از `MutableList` برای ذخیره لیستی از کاربران استفاده می‌کنیم و عملیات **افزودن، حذف و نمایش کاربران** را انجام می‌دهیم.  

```kotlin
data class User(
    val id: Int,
    val name: String,
    val email: String
)

fun main() {
    val users = mutableListOf(
        User(1, "علی ", "ali.111@example.com"),
        User(2, "سعید ", "saeid.222@example.com")
    )

    println("لیست اولیه کاربران:")
    users.forEach { println(it) }

    val newUser = User(3, "محمد ", "mohammad@example.com")
    users.add(newUser)
    println("\nپس از افزودن کاربر جدید:")
    users.forEach { println(it) }

    val userIdToRemove = 1
    users.removeIf { it.id == userIdToRemove }
    println("\nپس از حذف کاربر با شناسه $userIdToRemove:")
    users.forEach { println(it) }
}
```

---

### **توضیح کد:**  
1. یک `mutableListOf` از کاربران ایجاد شده است.  
2. کاربران اولیه در لیست نمایش داده می‌شوند.  
3. یک کاربر جدید (`newUser`) به لیست اضافه می‌شود.  
4. یک کاربر بر اساس `id` از لیست حذف می‌شود.  
5. لیست نهایی بعد از حذف نمایش داده می‌شود.  

✅ **با اجرای این برنامه، شما می‌توانید مدیریت کاربران را در یک آرایه قابل تغییر (`MutableList`) تجربه کنید.** 🚀

---
