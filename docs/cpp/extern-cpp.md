---
title: extern (C++)
description: Руководствуясь ключевым C++ словом Language extern.
ms.date: 01/28/2020
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- extern
- const
- constexpr
- permissive
ms.openlocfilehash: 422b6960802c59f1c45e0c22a4a85988c808a5b3
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821770"
---
# <a name="opno-locextern-c"></a>extern (C++)

Ключевое слово **extern** может быть применено к глобальной переменной, функции или объявлению шаблона. Он указывает, что символ имеет *внешнюю компоновку*. Дополнительные сведения о компоновке и о том, почему не рекомендуется использовать глобальные переменные, см. в разделе [Преобразование единиц и компоновки](program-and-linkage-cpp.md).

Ключевое слово **extern** имеет четыре значения в зависимости от контекста:

- В объявлении глобальной переменной, не являющейся **const** , **extern** указывает, что переменная или функция определена в другой записи преобразования. **extern** должны быть применены во всех файлах, кроме тех, в которых определена переменная.

- В объявлении переменной **const** указывает, что переменная имеет внешнюю компоновку. **extern** должны применяться ко всем объявлениям во всех файлах. (Глобальные переменные **const** по умолчанию имеют внутреннюю компоновку.)

- **extern "C"** указывает, что функция определена в других местах и использует соглашение о вызовах на языке C. Модификатор extern "C" также можно применить к нескольким объявлениям функций в блоке.

- В объявлении шаблона **extern** указывает, что шаблон уже создан в других местах. **extern** сообщает компилятору, что он может повторно использовать другое создание экземпляра, вместо того чтобы создавать новый экземпляр в текущем расположении. Дополнительные сведения об этом использовании **extern** см. в разделе [явное создание экземпляра](explicit-instantiation.md).

## <a name="opno-locextern-linkage-for-non-opno-locconst-globals"></a>externая компоновка для неconstных глобальных элементов

Когда компоновщик видит **extern** перед объявлением глобальной переменной, он ищет определение в другой записи преобразования. Объявления переменных, отличных от **const** , в глобальной области являются внешними по умолчанию. Применяйте **extern** только к объявлениям, не предоставляющим определение.

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

## <a name="opno-locextern-linkage-for-opno-locconst-globals"></a>extern компоновку для const глобальных элементов

**const** глобальная переменная по умолчанию имеет внутреннюю компоновку. Если требуется, чтобы переменная имела внешнюю компоновку, примените к определению ключевое слово **extern** , а также ко всем остальным объявлениям в других файлах:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="opno-locextern-opno-locconstexpr-linkage"></a>extern constexpr компоновка

В Visual Studio 2017 версии 15,3 и более ранних версиях компилятор всегда присвоил **constexpr** переменной внутреннюю компоновку, даже если переменная была помечена как **extern** . В Visual Studio 2017 с версией 15,5 и более поздней версии параметр компилятора [/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) обеспечивает правильное поведение соответствия стандартам. В конечном итоге параметр будет иметь значение по умолчанию. [/permissive-](../build/reference/permissive-standards-conformance.md) не включает параметр **/Zc: externConstexpr**.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Если файл заголовка содержит переменную, объявленную **extern** **constexpr** , она должна быть помечена как `__declspec(selectany)` для правильного объединения его повторяющихся объявлений:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="opno-locextern-c-and-opno-locextern-c-function-declarations"></a>объявления функций extern "C" иC++"extern"

В C++при использовании со строкой **extern** указывает, что для деклараторов используются соглашения компоновки другого языка. Доступ к функциям и данным C можно получить только в том случае, если они были ранее объявлены с компоновкой C. Однако они должны быть определены в блоке трансляции, который компилируется отдельно.

Корпорация C++ Майкрософт поддерживает строки **"C"** и **"C++"** в поле " *строковый литерал* ". Во всех стандартных включаемых файлах используется синтаксис **extern "C"** , позволяющий использовать функции библиотеки времени выполнения в C++ программах.

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

Если у функции несколько спецификаций компоновки, они должны быть согласованы. Объявление функций как C, так и C++ с компоновкой является ошибкой. Кроме того, если в программе имеются два объявления функции (одно со спецификацией компоновки, а другое без такой спецификации), объявление с указанием компоновки должен быть первым. Ко всем повторным объявлениям функций, уже имеющих спецификацию компоновки, применяется компоновка из первого объявления. Например:

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

[Ключевые слова](../cpp/keywords-cpp.md)\
[Единицы преобразования и\ компоновки](program-and-linkage-cpp.md)
[extern описатель класса хранения в C](../c-language/extern-storage-class-specifier.md)\
[Поведение идентификаторов в C](../c-language/behavior-of-identifiers.md)\
[Компоновка в C](../c-language/linkage.md)
