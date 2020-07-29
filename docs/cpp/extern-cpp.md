---
title: ':::no-loc(extern)::: (C++)'
description: 'Пошаговое руководством по :::no-loc(extern)::: ключевому слову языка C++.'
ms.date: 01/28/2020
f1_keywords:
- ':::no-loc(extern):::'
- :::no-loc(extern):::_CPP
helpviewer_keywords:
- ':::no-loc(extern)::: keyword [C++], linkage to non-C++ functions'
- declarations, :::no-loc(extern):::al
- ':::no-loc(extern):::al linkage, :::no-loc(extern)::: modifier'
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- ':::no-loc(extern):::'
- ':::no-loc(const):::'
- ':::no-loc(constexpr):::'
- ':::no-loc(permissive):::'
ms.openlocfilehash: 510352f9e99e513f4a426f6ef89be4474085d97c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227508"
---
# <a name="no-locextern-c"></a>:::no-loc(extern)::: (C++)

**`:::no-loc(extern):::`** Ключевое слово может быть применено к глобальной переменной, функции или объявлению шаблона. Он указывает, что символ имеет * :::no-loc(extern)::: связь Al*. Дополнительные сведения о компоновке и о том, почему не рекомендуется использовать глобальные переменные, см. в разделе [Преобразование единиц и компоновки](program-and-linkage-cpp.md).

**`:::no-loc(extern):::`** Ключевое слово имеет четыре значения в зависимости от контекста:

- В **`:::no-loc(const):::`** объявлении неглобальной переменной **`:::no-loc(extern):::`** указывает, что переменная или функция определена в другой записи преобразования. **`:::no-loc(extern):::`** Должен применяться ко всем файлам, за исключением того, где определена переменная.

- В **`:::no-loc(const):::`** объявлении переменной указывается, что переменная имеет :::no-loc(extern)::: связь Al. **`:::no-loc(extern):::`** Должен применяться ко всем объявлениям во всех файлах. ( **`:::no-loc(const):::`** По умолчанию глобальные переменные имеют внутреннюю компоновку.)

- ** :::no-loc(extern)::: "C"** указывает, что функция определена в других местах и использует соглашение о вызовах на языке C. :::no-loc(extern):::Модификатор "C" может также применяться к нескольким объявлениям функций в блоке.

- В объявлении шаблона **`:::no-loc(extern):::`** указывает, что шаблон уже создан в других местах. **`:::no-loc(extern):::`** сообщает компилятору, что он может повторно использовать другое создание экземпляра, вместо того чтобы создавать новый экземпляр в текущем расположении. Дополнительные сведения об этом использовании см **`:::no-loc(extern):::`** . в разделе [явное создание экземпляра](explicit-instantiation.md).

## <a name="no-locextern-linkage-for-non-no-locconst-globals"></a>:::no-loc(extern):::компоновка для :::no-loc(const)::: неглобальных элементов

Если компоновщик видит **`:::no-loc(extern):::`** перед объявлением глобальной переменной, он ищет определение в другой записи преобразования. Объявления **`:::no-loc(const):::`** непеременных в глобальной области :::no-loc(extern)::: по умолчанию имеют значение Al. Применяется только **`:::no-loc(extern):::`** к объявлениям, не предоставляющим определение.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileC.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
:::no-loc(extern)::: int i = 43; // same error (:::no-loc(extern)::: is ignored on definitions)
```

## <a name="no-locextern-linkage-for-no-locconst-globals"></a>:::no-loc(extern):::компоновка для :::no-loc(const)::: глобальных элементов

**`:::no-loc(const):::`** По умолчанию глобальная переменная имеет внутреннюю компоновку. Если требуется, чтобы переменная соимела :::no-loc(extern)::: связь Al, примените **`:::no-loc(extern):::`** к определению ключевое слово и ко всем остальным объявлениям в других файлах:

```cpp
//fileA.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i = 42; // :::no-loc(extern)::: :::no-loc(const)::: definition

//fileB.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i;  // declaration only. same as i in FileA
```

## <a name="no-locextern-no-locconstexpr-linkage"></a>:::no-loc(extern)::::::no-loc(constexpr):::компоновка

В Visual Studio 2017 версии 15,3 и более ранних версиях компилятор всегда присвоил **`:::no-loc(constexpr):::`** переменную внутреннюю компоновку, даже если переменная была помечена **`:::no-loc(extern):::`** . В Visual Studio 2017 версии 15,5 и более поздних параметр компилятора [/Zc: :::no-loc(extern)::: constexpr](../build/reference/zc-:::no-loc(extern)::::::no-loc(constexpr):::.md) обеспечивает правильное поведение соответствия стандартам. В конечном итоге параметр будет иметь значение по умолчанию. [/:::no-loc(permissive):::-](../build/reference/:::no-loc(permissive):::-standards-conformance.md)Параметр не включает **/Zc: :::no-loc(extern)::: constexpr**.

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: int x = 10; //error LNK2005: "int :::no-loc(const)::: x" already defined
```

Если файл заголовка содержит объявленную переменную **`:::no-loc(extern):::`** **`:::no-loc(constexpr):::`** , она должна быть помечена `__declspec(selectany)` для правильного объединения его повторяющихся объявлений:

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: __declspec(selectany) int x = 10;
```

## <a name="no-locextern-c-and-no-locextern-c-function-declarations"></a>:::no-loc(extern):::Объявления функций C и :::no-loc(extern)::: C++

В C++ при использовании со строкой **`:::no-loc(extern):::`** указывает, что для деклараторов используются соглашения компоновки другого языка. Доступ к функциям и данным C можно получить только в том случае, если они были ранее объявлены с компоновкой C. Однако они должны быть определены в блоке трансляции, который компилируется отдельно.

Microsoft C++ поддерживает строки **"C"** и **"C++"** в поле " *строковый литерал* ". Все стандартные включаемые файлы используют синтаксис ** :::no-loc(extern)::: "C"** , что позволяет использовать функции библиотеки времени выполнения в программах на C++.

## <a name="example"></a>Пример

В следующем примере показано, как объявить имена с компоновкой C:

```cpp
// Declare printf with C linkage.
:::no-loc(extern)::: "C" int printf(:::no-loc(const)::: char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
:::no-loc(extern)::: "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
:::no-loc(extern)::: "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
:::no-loc(extern)::: "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

:::no-loc(extern)::: "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
:::no-loc(extern)::: "C" int errno;
```

Если у функции несколько спецификаций компоновки, они должны быть согласованы. Объявление функций как с помощью компоновки C, так и с + + является ошибкой. Кроме того, если в программе имеются два объявления функции (одно со спецификацией компоновки, а другое без такой спецификации), объявление с указанием компоновки должен быть первым. Ко всем повторным объявлениям функций, уже имеющих спецификацию компоновки, применяется компоновка из первого объявления. Пример:

```cpp
:::no-loc(extern)::: "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
:::no-loc(extern)::: "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>См. также раздел

[Словами](../cpp/keywords-cpp.md)\
[Единицы и компоновка преобразований](program-and-linkage-cpp.md)\
[:::no-loc(extern):::Описатель класса хранения в C](../c-language/:::no-loc(extern):::-storage-class-specifier.md)\
[Поведение идентификаторов в C](../c-language/behavior-of-identifiers.md)\
[Компоновка в C](../c-language/linkage.md)
