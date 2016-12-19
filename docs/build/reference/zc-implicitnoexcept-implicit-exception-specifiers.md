---
title: "/Zc:implicitNoexcept (неявные спецификаторы исключений) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:implicitNoexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc:implicitNoexcept"
  - "Zc:implicitNoexcept"
  - "-Zc:implicitNoexcept"
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:implicitNoexcept (неявные спецификаторы исключений)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если параметр **\/Zc:implicitNoexcept** указан, компилятор добавляет неявный описатель исключения [noexcept](../Topic/noexcept%20\(C++\).md) в заданные компилятором специальные функции\-члены и пользовательские деструкторы и методы освобождения.  По умолчанию параметр **\/Zc:implicitNoexcept** включен для обеспечения соответствия стандарту ISO C\+\+ 11.  Отключение этого параметра отключает неявный `noexcept` для пользовательских деструкторов и методов освобождения, а также заданных компилятором специальных функций\-членов.  
  
## Синтаксис  
  
```vb  
/Zc:implicitNoexcept[-]  
```  
  
#### Параметры  
  
## Заметки  
 По умолчанию и при указании параметра **\/Zc:implicitNoexcept** компилятор следует разделу 15.4 стандарта ISO C\+\+ 11 и неявным образом добавляет описатель исключения `noexcept` в каждую объявленную неявно или явно установленную по умолчанию специальную функцию\-член — конструктор по умолчанию, конструктор копии, конструктор перемещения, деструктор, оператор присваивания при копировании или оператор присваивания при перемещении — и каждый пользовательский деструктор или функцию освобождения.  Определяемый пользователем метод освобождения содержит неявный описатель исключения `noexcept(true)`.  Для пользовательских деструкторов неявный описатель исключение — `noexcept(true)`, если во внутреннем классе члена или базовом классе нет деструктора, отличного от типа `noexcept(true)`.  Если для созданных компилятором специальных функций\-членов любая функция, вызываемая напрямую этой функцией, фактически является `noexcept(false)`, а неявный описатель исключения — `noexcept(false)`.  Иначе неявный описатель исключение — `noexcept(true)`.  
  
 Компилятор не создает неявный описатель исключения для функций, объявленных с явными описателями `noexcept` и `throw` или атрибутом `__declspec(nothrow)`.  
  
 Если этот параметр отключен \(указан **\/Zc:implicitNoexcept\-**\), компилятор не создает неявные описатели исключений.  То же самое происходит в Visual Studio 2013, где в деструкторах и методах освобождения без описателей исключений могли быть операторы `throw`.  По умолчанию и при указании **\/Zc:implicitNoexcept**, если во время выполнения в функции с неявным описателем `noexcept(true)` встречается `throw`, немедленно вызывается `std::terminate`, при этом нормальное поведение очистки для обработчиков исключений не гарантируется.  Для идентификации этой ситуации компилятор создает [Предупреждение компилятора \(уровень 1\) C4297](../Topic/Compiler%20Warning%20\(level%201\)%20C4297.md).  Если `throw` вызывается преднамеренно, мы рекомендуем использовать в объявлении функции явный описатель `noexcept(false)` вместо **\/Zc:implicitNoexcept\-**.  
  
 В этом примере показано, как пользовательский деструктор без явного описателя исключения, ведет себя, если параметр **\/Zc:implicitNoexcept** задан или отключен.  Для демонстрации поведения при указании параметра выполните компиляцию с помощью `cl/EHsc /W4 implicitNoexcept.cpp`.  Для демонстрации поведения при отключении параметра выполните компиляцию с помощью `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.  
  
```  
// implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp  
  
#include <iostream>  
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS  
#include <exception>    // for std::set_terminate  
  
void my_terminate()  
{  
    std::cout << "Unexpected throw caused std::terminate" << std::endl;  
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;  
    std::exit(EXIT_FAILURE);  
}  
  
struct A {  
    // Explicit noexcept overrides implicit exception specification  
    ~A() noexcept(false) {  
        throw 1;  
    }  
};  
  
struct B : public A {  
    // Compiler-generated ~B() definition inherits noexcept(false)  
    ~B() = default;  
};  
  
struct C {  
    // By default, the compiler generates an implicit noexcept(true)  
    // specifier for this user-defined destructor. To enable it to  
    // throw an exception, use an explicit noexcept(false) specifier,  
    // or compile by using /Zc:implicitNoexcept-  
    ~C() {    
        throw 1; // C4297, calls std::terminate() at run time  
    }  
};  
  
struct D : public C {  
    // This destructor gets the implicit specifier of its base.  
    ~D() = default;  
};  
  
int main()  
{  
    std::set_terminate(my_terminate);  
  
    try  
    {  
        {  
            B b;   
        }  
    }  
    catch (...)  
    {  
        // exception should reach here in all cases  
        std::cout << "~B Exception caught" << std::endl;  
    }  
    try  
    {  
        {  
            D d;  
        }  
    }  
    catch (...)  
    {  
        // exception should not reach here if /Zc:implicitNoexcept  
        std::cout << "~D Exception caught" << std::endl;  
    }  
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;  
    return EXIT_SUCCESS;  
}  
  
```  
  
 При компиляции с параметром по умолчанию **\/Zc:implicitNoexcept** пример формирует следующие выходные данные:  
  
  **Перехвачено исключение ~B**  
**Непредвиденный вызов привел к std::terminate**  
**При выходе возвращается EXIT\_FAILURE** При компиляции с параметром **\/Zc:implicitNoexcept\-** пример формирует следующие выходные данные:  
  
  **Перехвачено исключение ~B**  
**Перехвачено исключение ~B**  
**При выходе возвращается EXIT\_SUCCESS** Подробнее о вопросах соответствия в Visual C\+\+ см. в статье [Нестандартное поведение](../Topic/Nonstandard%20Behavior.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Измените свойство **Дополнительные параметры**, добавив параметр **\/Zc:implicitNoexcept** или **\/Zc:implicitNoexcept\-**, а затем нажмите кнопку **ОК**.  
  
## См. также  
 [\/Zc \(соответствие\)](../../build/reference/zc-conformance.md)   
 [noexcept](../Topic/noexcept%20\(C++\).md)   
 [Спецификации исключений \(throw\)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../Topic/terminate%20\(%3Cexception%3E\).md)