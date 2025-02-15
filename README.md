# **آموزش مقدماتی کاتلین – جلسه دوم** 🚀

## **مقدمه**

در این جلسه، مفاهیم پیشرفته‌تری از کاتلین را بررسی خواهیم کرد. مباحث امروز شامل **آرایه‌ها، لیست‌ها، توابع، Null Safety و let در کاتلین** خواهد بود.

---

## **۱. آرایه‌ها و لیست‌ها** 📦

### **آرایه‌ها در کاتلین**

```kotlin
val numbers = arrayOf(1, 2, 3, 4, 5)
println(numbers[0]) // دسترسی به اولین مقدار
numbers[2] = 10    // تغییر مقدار عنصر سوم
```

### **لیست‌ها در کاتلین**

```kotlin
val names = listOf("Ali", "Reza", "Sara") // لیست غیرقابل تغییر
val mutableNames = mutableListOf("Ali", "Reza") // لیست قابل تغییر
mutableNames.add("Sara")
```

✏️ **تمرین ۱ (ساده)**: برنامه‌ای بنویسید که یک لیست از اعداد دریافت کند و مجموع آن‌ها را محاسبه کند.

### **راه‌حل پیشنهادی:**

```kotlin
fun main() {
    val numbers = listOf(1, 2, 3, 4, 5)
    val sum = numbers.sum()
    println("مجموع اعداد: $sum")
}
```

✏️ **تمرین ۲ (پیچیده‌تر)**: برنامه‌ای بنویسید که یک لیست از اعداد دریافت کند و بزرگ‌ترین مقدار را برگرداند.

### **راه‌حل پیشنهادی:**

```kotlin
fun main() {
    val numbers = listOf(12, 45, 2, 78, 33)
    val maxNumber = numbers.maxOrNull()
    println("بزرگ‌ترین عدد: $maxNumber")
}
```

---

## **۲. توابع در کاتلین** 🔧

### **ایجاد یک تابع ساده**

```kotlin
fun greet(name: String) {
    println("سلام، $name!")
}

greet("سعید")
```

✏️ **تمرین ۳ (ساده)**: تابعی بنویسید که یک نام دریافت کند و آن را با عبارت "سلام" نمایش دهد.

### **راه‌حل پیشنهادی:**

```kotlin
fun greet(name: String) {
    println("سلام، $name!")
}

fun main() {
    greet("رضا")
}
```

---

## **۳. Null Safety در کاتلین** ⚠️

در کاتلین، متغیرها می‌توانند `null` باشند یا نباشند. استفاده از `null` به شکل ایمن باعث کاهش خطای `NullPointerException` می‌شود.

### **مثالی از مقدار nullable و non-nullable**

```kotlin
var name: String = "Saeid" // غیر قابل null شدن
var nullableName: String? = null // قابل null شدن
```

### **استفاده از `?.` برای بررسی مقدار null**

```kotlin
val length: Int? = nullableName?.length
println("طول رشته: $length")
```

✏️ **تمرین ۴ (متوسط)**: تابعی بنویسید که یک نام دریافت کند و اگر مقدار `null` بود، مقدار پیش‌فرض "ناشناس" را نمایش دهد.

### **راه‌حل پیشنهادی:**

```kotlin
fun printName(name: String?) {
    println("سلام، ${name ?: "ناشناس"}!")
}

fun main() {
    printName(null)
    printName("رضا")
}
```

---

## **۴. استفاده از `let` در کاتلین** 🔄

تابع `let` در کاتلین برای اجرای یک عملیات روی یک مقدار nullable استفاده می‌شود. درصورتی‌که مقدار `null` نباشد، کد داخل `let` اجرا خواهد شد.

### **نمونه‌ای از `let` برای مقدار nullable**

```kotlin
val name: String? = "Saeid"
name?.let {
    println("نام شما: $it")
}
```

### **تمرین ۵ (متوسط)**: برنامه‌ای بنویسید که اگر مقدار یک رشته `null` نبود، طول آن را نمایش دهد.

### **راه‌حل پیشنهادی:**

```kotlin
fun printLength(text: String?) {
    text?.let {
        println("طول رشته: ${it.length}")
    }
}

fun main() {
    printLength("Hello, Kotlin!")
    printLength(null)
}
```

📌 در این جلسه با **آرایه‌ها، لیست‌ها، توابع، Null Safety و let** آشنا شدیم. در جلسه بعد وارد مباحث پیشرفته‌تر خواهیم شد. 🚀

💬 سوالی دارید؟ در **Issues** بپرسید یا Pull Request ارسال کنید! 😊

