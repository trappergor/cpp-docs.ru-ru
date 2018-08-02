---
title: extern (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 04/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
- extern_CPP
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 133cbb01ba54ccc8bc0ce0c31b5d7b4436c2488d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403054"
---
# <a name="extern-c"></a>extern (C++)

**Extern** на глобальное объявление переменной, функцией или шаблон, чтобы указать, что имя то есть применяется ключевое слово *внешнюю компоновку*. Сведения о компоновке и почему не рекомендуется использование глобальных переменных, см. в разделе [программа и компоновка](program-and-linkage-cpp.md).

**Extern** ключевое слово имеет четыре значения в зависимости от контекста:

1. в неконстантной глобального объявление переменной **extern** указывает, что переменная или функция определен в другой записи преобразования. **Extern** должны применяться во всех файлах за исключением того, где определена переменная.
1. в объявлении переменной const он указывает, что переменная имеет внешнюю компоновку. **Extern** должны применяться ко всем объявлениям во всех файлах. (Глобальные переменные const имеют внутреннюю компоновку по умолчанию).
1. **extern «C»** указывает, что функция определена в другом месте и использует соглашение о вызове языка C. Модификатор extern «C» также может применяться к нескольким объявления функций в блоке.
1. в объявлении шаблона он указывает, что шаблон уже создан в другом месте. Это оптимизация, который сообщает компилятору, что можно повторно использовать другим экземпляром, а не создавать новую в текущем положении. Дополнительные сведения о такое использование **extern**, см. в разделе [шаблоны](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>компоновка extern для неконстантной globals

Когда компоновщик обнаруживает **extern** до глобального объявления переменной, он ищет в определении в другой записи преобразования. Объявления переменных неконстантной в глобальной области являются внешними по умолчанию; применяются только **extern** объявления, которые не предоставляют определение.

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

## <a name="extern-linkage-for-const-globals"></a>компоновка extern для const globals

Объект **const** глобальная переменная имеет внутреннюю компоновку по умолчанию. Если необходимо задать для переменной внешнюю компоновку, примените **extern** ключевое слово к определению, а также относительно всех других объявлений в других файлах:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>компоновка extern constexpr

В Visual Studio 2017 версии 15.3 и более ранних версий компилятор всегда обеспечивал внутреннюю компоновку constexpr переменной, даже в том случае, когда переменная была помечена как extern. В Visual Studio 2017 версии 15.5 новый параметр компилятора ([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)) обеспечивает корректное поведение, соответствующее стандартам. В конечном счете это будет поведением по умолчанию.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Если файл заголовка содержит переменную объявленного extern constexpr, она должна быть отмечена как **__declspec(selectany)** для правильного объединения повторяющихся объявлений:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>объявления функции extern «C» "и" extern «C++»

 В C++, при использовании со строкой **extern** указывает, что для компоновках используются соглашения о другом языке. К функциям и данным C можно обращаться, только если ранее они были объявлены как имеющие компоновки C. Однако они должны быть определены в блоке трансляции, который компилируется отдельно.

 Microsoft C++ поддерживаются строки **«C»** и **«C++»** в *строковый литерал* поля. Всех стандартных включаемых файлах используется **extern** синтаксис «C», чтобы разрешить функций библиотеки времени выполнения, которые используются в программах на C++.

## <a name="example"></a>Пример

В следующем примере показано, как объявления имен, которые имеют компоновки:

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

 Если у функции несколько спецификаций компоновки, они должны быть согласованы; если для функции объявлены компоновки C и C++ — это ошибка. Кроме того, если в программе имеются два объявления функции (одно со спецификацией компоновки, а другое без такой спецификации), объявление с указанием компоновки должен быть первым. Ко всем повторным объявлениям функций, уже имеющих спецификацию компоновки, применяется компоновка из первого объявления. Пример:

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

## <a name="see-also"></a>См. также
 [Ключевые слова](../cpp/keywords-cpp.md)  
 [Программа и компоновка](program-and-linkage-cpp.md)  
 [extern спецификатор класса хранения в C](../c-language/extern-storage-class-specifier.md)  
 [Поведение идентификаторов в C](../c-language/behavior-of-identifiers.md)  
 [Компоновка в C](../c-language/linkage.md)