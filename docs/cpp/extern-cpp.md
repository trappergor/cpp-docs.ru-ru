---
title: extern (C++)
ms.date: 04/12/2018
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
ms.openlocfilehash: d42a32202f7fa67751ea36757c13b2c6af4953b2
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301539"
---
# <a name="extern-c"></a>extern (C++)

Ключевое слово **extern** применяется к объявлению глобальной переменной, функции или шаблона, чтобы указать, что имя этой вещи имеет *внешнюю компоновку*. Дополнительные сведения о компоновке и о том, почему не рекомендуется использовать глобальные переменные, см. в разделе [Преобразование единиц и компоновки](program-and-linkage-cpp.md).

Ключевое слово **extern** имеет четыре значения в зависимости от контекста:

1. в объявлении неконстантной глобальной переменной ключевое поле **extern** указывает, что переменная или функция определена в другой записи преобразования. **Модификатор extern** должен применяться ко всем файлам, кроме тех, в которых определена переменная.
1. в объявлении переменной const указывается, что переменная имеет внешнюю компоновку. **Модификатор extern** должен применяться ко всем объявлениям во всех файлах. (Глобальные переменные const по умолчанию имеют внутреннюю компоновку.)
1. **extern "C"** указывает, что функция определена в других местах и использует соглашение о вызовах на языке C. Модификатор extern "C" также может применяться к нескольким объявлениям функций в блоке.
1. в объявлении шаблона указывает, что шаблон уже создан в других местах. Это оптимизация, которая сообщает компилятору, что он может повторно использовать другой экземпляр, а не создавать новый объект в текущем расположении. Дополнительные сведения об этом использовании **extern**см. в разделе [шаблоны](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>Внешние компоновки для неконстантных глобальных элементов

Когда компоновщик видит **модификатор extern** перед объявлением глобальной переменной, он ищет определение в другой записи преобразования. Объявления переменных, не являющихся константами, в глобальной области по умолчанию являются внешними. Используйте **модификатор extern** только для объявлений, не предоставляющих определение.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="extern-linkage-for-const-globals"></a>Внешние компоновки для глобальных констант

По умолчанию **константа** глобальной переменной имеет внутреннюю компоновку. Если требуется, чтобы переменная имела внешнюю компоновку, примените к определению ключевое слово **extern** , а также ко всем остальным объявлениям в других файлах:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>Компоновка внешнего constexpr

В Visual Studio 2017 версии 15,3 и более ранних версиях компилятор всегда дал переменную внутренней компоновки constexpr, даже если переменная была помечена как extern. В Visual Studio 2017 версии 15.5 новый параметр компилятора ([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)) обеспечивает корректное поведение, соответствующее стандартам. В конечном счете это будет поведением по умолчанию. Параметр/permissive-не включает/Zc: externConstexpr.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Если файл заголовка содержит переменную, объявленную как extern constexpr, она должна быть помечена как **__declspec (selectany)** для правильного объединения его повторяющихся объявлений:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>объявления функций extern "C" иC++extern ""

В C++при использовании со строкой **модификатор extern** указывает, что для деклараторов используются соглашения компоновки другого языка. К функциям и данным C можно обращаться, только если ранее они были объявлены как имеющие компоновки C. Однако они должны быть определены в блоке трансляции, который компилируется отдельно.

Корпорация C++ Майкрософт поддерживает строки **"C"** и **"C++"** в поле " *строковый литерал* ". Все стандартные включаемые файлы используют **внешний** синтаксис "C", позволяющий использовать функции библиотеки времени выполнения в C++ программах.

## <a name="example"></a>Пример

В следующем примере показано, как объявить имена с компоновкой C:

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

Если у функции несколько спецификаций компоновки, они должны быть согласованы; если для функции объявлены компоновки C и C++ — это ошибка. Кроме того, если в программе имеются два объявления функции (одно со спецификацией компоновки, а другое без такой спецификации), объявление с указанием компоновки должен быть первым. Ко всем повторным объявлениям функций, уже имеющих спецификацию компоновки, применяется компоновка из первого объявления. Например:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Единицы и компоновка преобразований](program-and-linkage-cpp.md)<br/>
[Спецификатор класса хранения extern в C](../c-language/extern-storage-class-specifier.md)<br/>
[Поведение идентификаторов в C](../c-language/behavior-of-identifiers.md)<br/>
[Компоновка в C](../c-language/linkage.md)