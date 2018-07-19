---
title: extern (C++) | Документы Microsoft
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
ms.openlocfilehash: 00b9f94d02443163f45b83d64702fe49622597cd
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261080"
---
# <a name="extern-c"></a>extern (C++)

**Extern** глобальные объявления переменной, функции или шаблона, чтобы указать, что это имя имеет применяется ключевое слово *внешней компоновки*. Сведения о компоновке и почему не рекомендуется использование глобальных переменных см. в разделе [программа и компоновка](program-and-linkage-cpp.md).

**Extern** ключевое слово имеет четыре значения в зависимости от контекста:

1. в неконстантной глобальные объявления переменных **extern** указывает, что переменная или функция определена в другой записи преобразования. **Extern** должны применяться во всех файлах за исключением того, на котором определена переменная.
1. в объявлении переменной const он указывает, что переменная имеет внешнюю компоновку. **Extern** необходимо применить ко всем объявлениям во всех файлах. (Глобальных переменных const имеют внутреннюю компоновку по умолчанию).
1. **extern «C»** указывает, что функция определена в другом месте и использует соглашение о вызовах языка C. Модификатор extern «C» также может применяться к нескольким объявления функций в блоке.
1. в объявлении шаблона он указывает, что шаблон уже создан в другом месте. Это способ оптимизации, сообщает компилятору, его можно повторно использовать другим экземпляром, а не создавать новый в текущем положении. Дополнительные сведения об использовании этого **extern**, в разделе [шаблоны](templates-cpp.md).

## <a name="extern-linkage-for-non-const-globals"></a>внешнюю компоновку для неконстантной globals

Когда компоновщик обнаруживает **extern** до объявления глобальной переменной, она выполняет поиск определения в другой записи преобразования. Объявления переменных с неконстантной в глобальной области являются внешними по умолчанию; применяются только **extern** для объявлений, которые не предоставляют определение.

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

## <a name="extern-linkage-for-const-globals"></a>внешнюю компоновку для const globals

Объект **const** глобальная переменная имеет внутреннюю компоновку по умолчанию. Если необходимо задать для переменной внешнюю компоновку, примените **extern** ключевое слово для определения также относительно всеми остальными объявлениями в других файлах:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>Внешнюю компоновку constexpr

В Visual Studio 2017 г. версия 15,3 и более ранних версий компилятор всегда было присвоено переменной внутренней компоновкой constexpr даже в том случае, когда переменная была помечена extern. В Visual Studio 2017 версии 15.5 новый параметр компилятора ([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)) обеспечивает корректное поведение, соответствующее стандартам. В конечном счете это будет поведением по умолчанию.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Если файл заголовка содержит constexpr переменной объявленного extern, она должна быть отмечена как **__declspec(selectany)** для выполнения правильно его повторяющихся объявлений вместе:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>объявления функции extern «C» и «C++» extern

 В C++, при использовании со строкой **extern** указывает, для компоновках используются соглашения компоновки другого языка. К функциям и данным C можно обращаться, только если ранее они были объявлены как имеющие компоновки C. Однако они должны быть определены в блоке трансляции, который компилируется отдельно.

 Microsoft C++ поддерживаются строки **«C»** и **«C++»** в *строковый литерал* поля. Всех стандартных включаемых файлах используется **extern** синтаксис «C», чтобы разрешить функций библиотеки времени выполнения, которые используются в программах на C++.

## <a name="example"></a>Пример

В следующем примере показан способ объявления имена с компоновкой C:

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

- [Ключевые слова](../cpp/keywords-cpp.md)
- [Программа и компоновка](program-and-linkage-cpp.md)
- [extern спецификатор класса хранения в C](../c-language/extern-storage-class-specifier.md) 
- [Поведение идентификаторов в C](../c-language/behavior-of-identifiers.md) 
- [Компоновка в C](../c-language/linkage.md)