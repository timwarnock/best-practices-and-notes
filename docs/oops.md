# End of OOP

Object Oriented Programming has been a disaster for Software Engineering.

## OOP versus Procedural

I would like to know when it is best to use object-oriented programming, and when it is best to use procedural programming.

tl;dr: neither, go with functional programming

By procedural programming, I mean the kind of code you'd find programming in C; imperative control flow, functions, data structures, and algorithms. For example,

```c
#include <stdio.h>

float f_to_c(float f) {
    return (f - 32) * 5 / 9;
}

int main() {
    float fahrenheit;
    printf("Please enter the temperature in Fahrenheit: ");
    scanf("%f", &fahrenheit);
    printf("Temperature in Celsius = %.2f\n", f_to_c(fahrenheit));
    return 0;
}
```

And by object-oriented programming, I mean the kind of code with abstraction, inheritance, polymorphism, and encapsulation. For example,

```java
import java.util.*;

interface TemperatureConverter {
    public float convert();
}

class Temperature {
    float degrees;
    Temperature(float t) {
        degrees = t;
    }
}

class Fahrenheit extends Temperature implements TemperatureConverter {

    Fahrenheit(float t) {
        super(t);
    }

    public float convert() {
        return ((degrees - 32)*5)/9;
    }

}

class FahrenheitToCelsius {

    public static void main(String[] args) {
        Fahrenheit fahrenheit;
        Scanner in = new Scanner(System.in);
        System.out.print("Enter temperature in Fahrenheit: ");
        fahrenheit = new Fahrenheit( in.nextFloat() );

        System.out.println("temperature in Celsius = " 
            + fahrenheit.convert());
    }

}
```

I admittedly forced some inheritance and polymorphism into the above code, but it's arguably just as easy (if not easier) to read than the C example (despite being considerably longer).

In both cases we hid the implementation details (the specific formula that converts Fahrenheit to Celsius) from the main(). However, the OOP example also hides (encapsulates) the data structure as well. In the Java example we encapsulate the float within the Temperature base class, which the Fahrenheit class inherits. And since the Fahrenheit class implements the TemperatureConverter interface, then we're guaranteed to have a convert() method. There is still some implicit typecasting (a float to string within the println), but the idea is that the main() function doesn't care about the underlying data structure.

As Robert Martin (Uncle Bob) put it, "Objects expose behavior and hide data." The Fahrenheit class exposed a convert() behavior and hid the underlying data structure. This, according to Uncle Bob, makes it easy to add new objects without changing existing behaviors. For example,

class Celsius extends Temperature implements TemperatureConverter {

    Celsius(float t) {
        super(t);
    }

    public float convert() {
        return 9*degrees/5 + 32;
    }

}
This code has no impact on the existing Fahrenheit class, and we can safely call convert() on both Fahrenheit and Celsius objects. Additionally, if we use generics on the Temperature class, then we could allow for different data structures (such as double or BigDecimal) on something like a Kelvin class. In OOP, adding new classes is generally easy.

That said, what if we wanted to add new behavior? Maybe we want to add an isRoomTemperature() method. If so, we could add a new interface and then implement it in Celsius and Fahrenheit, but what if we had also implemented that new Kelvin class? Or several other Temperature classes? And shouldn't the convert() method return a Temperature class? This could get messy and will lead us into DRY problems. In fact, this is an area where OOP is not ideal. Even Uncle Bob admits that if we're adding new behaviors then "we prefer data types and procedures."

This seemingly obvious and innocuous statement in Clean Code is actually very profound, especially considering the fact that OOP and classic procedural programming do not mix well in a single code-base. Whether you go with OOP or not, if Uncle Bob is correct, depends on whether or not you will be adding and managing lots of behavior, or whether you will be adding and managing lots of data types. If the behavior will be relatively unchanged, then OOP would be beneficial, but if we're planning to add or change behavior, then procedural programming would be preferred. I honestly don't know what kind of software projects aren't primarily adding new behaviors (new features).

For reference, adding a room temperature check is easy in the C code,

#include <stdio.h>
#include <stdbool.h>

bool is_c_room_temperature(float c) {
    return c >= 20 && c <= 25 ? 1 : 0;
}

float f_to_c(float f) {
    return (f - 32) * 5 / 9;
}

bool is_f_room_temperature(float f) {
    return is_c_room_temperature(f_to_c(f));
}

int main() {
    float fahrenheit;
    printf("Please enter the temperature in Fahrenheit: ");
    scanf("%f", &fahrenheit);
    printf("Temperature in Celsius = %.2f\n", f_to_c(fahrenheit));
    if (is_f_room_temperature(fahrenheit)) {
        printf("%.2f is room temperature\n", fahrenheit);
    }
    return 0;
}
Classic procedural code does not concern itself with adding behaviors to objects. Instead, it treats data types as data types and isolates the "procedural" behaviors into functions that are performed on those data types. If we stick to pure functions (no side effects, and all inputs map to unique outputs), then we'll have highly testable code that can run in highly-concurrent environments.

For example, adding a Kelvin conversion would look like this,

float c_to_k(float c) {
    return c + 273.15;
}
Likewise, adding a Fahrenheit to Kelvin conversion would simply chain together two pure functions,

float f_to_k(float f) {
    return c_to_k(f_to_c(f));
}
Procedural code focuses entirely on behavior. Adding this functionality in a pure OOP style would result a laundry list of classes, interfaces, and methods. It can get out of hand quickly, and we'd soon be researching design patterns to try to regain some sense of code quality.

In practice, most developers tend to treat OOP and procedural programming with a sort of religious devotion, zealously adhering to their preferred programming style and feeling that the alternative is sacrilege. I think Uncle Bob was onto something when he said that "good software developers understand these issues without prejudice and choose the approach that is best for the job at hand." That's also from Clean Code, a book that should be read at least as often as it's referenced (it's a bit like George Orwell's 1984, most people reference it without ever having read it).

Uncle Bob is certainly more diplomatic than Joe Armstrong, the creator of Erlang, who had famously said,

"The problem with object-oriented languages is they’ve got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle."

To date, I've never heard a reasonable counter-argument to this objection to OOP, namely, that objects bind data structures and functions together (which inevitably leads to an explosion of side-effects). Even as you try to decouple the banana from the gorilla, you end up creating even more classes, more side effects, and most likely an even worse problem. I'm not sure I'd go so far as to say OO Sucks, but I am hard pressed to defend OOP in light of decades of hard learned lessons.

Obviously, good code is preferable to bad code in any language. There is plenty of bad procedural code out in the world. But honestly, in OOP you often find good programmers writing bad code. Let's go back to some of the earliest lessons in software engineering, specifically, Fred Brook's essay, No Silver Bullet, and ask ourselves how much accidental complexity has been created by OOP? How much code in an average OOP project is tackling the essential complexity of a problem versus the accidental complexity?

In fairness, OOP was popularized by Java, which solved many problems from the early days of C and C++ (such as garbage collection and platform independence). In the decades since, Java has added capabilities found in modern languages (such as lambda expressions, collections, stream api, higher-order functions, etc). Most of the new capabilities come from the world of functional programming, and exactly zero of these capabilities come from OOP.

Whether we like it or not, the future may not be kind to OOP. Multi-core architectures and distributed computing are pushing software into high-concurrency asynchronous environments. Even worse, the push to cloud computing and microservices leads us to an increase in latency within a highly concurrent asynchronous world. This is an ideal environment for a separation of data structures from functions (pure functions). This is a great environment for Haskell and Erlang (or coding pure functions using Scala, Python, or Go), but regardless of the language, you couldn't ask for a worse environment for OOP.

