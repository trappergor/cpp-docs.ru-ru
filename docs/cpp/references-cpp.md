---
title: Ссылки (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9bd01cf5c153fcd31bae1a73fead87fe480cdd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030431"
---
# <a name="references-c"></a>Ссылки (C++)

В ссылке, как и в указателе, хранится адрес объекта, расположенного в другой области памяти. В отличие от указателя, после инициализации ссылку нельзя перенаправить на другой объект или присвоить ей нулевое значение. Существует два типа ссылок: ссылки lvalue, указывающие на именованные переменной и ссылки rvalue, указывающие на [временный объект](../cpp/temporary-objects.md). Оператором & обозначаются ссылки lvalue, а оператором &&, в зависимости от контекста, — ссылки rvalue или универсальные ссылки (как rvalue, так и lvalue).

Ссылки могут объявляться с помощью следующего синтаксиса.

```
[storage-class-specifiers] [cv-qualifiers] type-specifiers 
[ms-modifier] declarator [= expression];
```

Можно использовать любой допустимый декларатор, задающий ссылку. Следующий упрощенный синтаксис применяется всегда, кроме случаев, когда ссылка является ссылкой на функцию или тип массива.

```
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&] 
[cv-qualifiers] identifier [= expression];
```

Ссылки объявляются с использованием следующей последовательности.

1. Спецификаторы объявления:

- Необязательный спецификатор класса хранения.

- Необязательный **const** и/или **volatile** квалификаторы.

- Спецификатор типа: имя типа.

- 2. Декларатор:

- Необязательный модификатор, используемый в системах Microsoft. Дополнительные сведения см. в разделе [модификаторы, используемые Microsoft](../cpp/microsoft-specific-modifiers.md).

- Оператор & или &&.

- Необязательный **const** и/или **volatile** и(или).

- Идентификатор.

3. Необязательный инициализатор.

Более сложные формы декларатора для указателей на массивы и функции также применяются к ссылкам на массивы и функции, см. в разделе [указатели](../cpp/pointers-cpp.md).

Несколько деклараторов и инициализаторов могут отображаться в разделенном запятыми списке после отдельного спецификатора объявления. Пример:

```cpp
int &i;
int &i, &j;
```

Ссылки, указатели и объекты могут быть объявлены вместе.

```cpp
int &ref, *ptr, k;
```

Ссылка содержит адрес объекта, однако с синтаксической точки зрения ведет себя как объект.

В следующей программе обратите внимание, что имя объекта, `Today` и ссылка на объект, `TodayRef`, могут использоваться идентично в следующих программах.

## <a name="example"></a>Пример

```cpp
// references.cpp
#include <stdio.h>
struct S {
   short i;
};

int main() {
   S  s;   // Declare the object.
   S& SRef = s;   // Declare the reference.
   s.i = 3;

   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);

   SRef.i = 4;
   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);
}
```

```Output
3
3
4
4
```

## <a name="see-also"></a>См. также

[Аргументы функции ссылочного типа](../cpp/reference-type-function-arguments.md)<br/>
[Возвращаемые значения функции ссылочного типа](../cpp/reference-type-function-returns.md)<br/>
[Ссылки на указатели](../cpp/references-to-pointers.md)

