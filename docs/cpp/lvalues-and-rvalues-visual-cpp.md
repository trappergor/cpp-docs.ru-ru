---
title: 'Значение категории: Значения lvalue и rvalue (Visual C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed6f9a11b6cf2a0045729acbc79d8e45103064ea
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940190"
---
# <a name="lvalues-and-rvalues-visual-c"></a>Значения lvalue и rvalue (Visual C++)

Каждое выражение C++, с типом, а также входит в *категории значений*. Значение категории являются основой для правил, компиляторы должны следовать при создании, копирование и перемещение временные объекты во время вычисления выражения.

 Стандарт C ++ 17 определяет категории значение выражения следующим образом:

- Объект *glvalue* представляет собой выражение, вычисление которого определяет удостоверение объекта, битового поля или функции.
- Объект *prvalue* представляет собой выражение, вычисление которого инициализирует объект или битовому полю или вычисляет значение операнда оператора, как указано в контексте, в котором он отображается.
- *Xvalue* является glvalue, который обозначает объект или битового поля, ресурсы которых может многократно использоваться (обычно, поскольку он находится в конце его времени существования). [Пример: некоторые типы выражений, включающих ссылки rvalue (8.3.2) yield xvalues, такие как вызов функции, возвращаемый тип которых является ссылкой rvalue или преобразование в ссылочный тип rvalue. ]
- *Lvalue* является glvalue, который не является xvalue.
- *Rvalue* prvalue или xvalue.

Следующей схеме показаны связи между категориями:

 ![Категории значение выражения C++](media/value_categories.png "категории значение выражения C++")

 Lvalue имеет адрес, который можно получить доступ к программе. Примеры выражений lvalue включают имена переменных, включая **const** переменных, элементов массива, функция вызовы, которые возвращают ссылки lvalue, битовые поля, объединения и членов класса.

 Выражение prvalue не имеет адреса, доступном в программе. Примеры выражений prvalue включают литералы, вызовы функций, возвращающих тип без ссылок и временные объекты, созданные во время вычислений выражения, но доступен только компилятором.

 Выражение xvalue имеет адрес, станут недоступными в программе, но может использоваться для инициализации ссылкой rvalue, который предоставляет доступ к выражению. Примеры вызовов функций, которые возвращают ссылку rvalue и индекс массива, член и указателя выражения элементов, где массива или объекта является ссылкой rvalue.

## <a name="example"></a>Пример

 В следующем примере показано несколько правильных и неправильных способов использования значений lvalue и rvalues.

```cpp
// lvalues_and_rvalues2.cpp
int main()
{
 int i, j, *p;

 // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.
 i = 7;

 // Incorrect usage: The left operand must be an lvalue (C2106).`j * 4` is a prvalue.
 7 = i; // C2106
 j * 4 = 7; // C2106

 // Correct usage: the dereferenced pointer is an lvalue.
 *p = i;

 const int ci = 7;
 // Incorrect usage: the variable is a non-modifiable lvalue (C3892).
 ci = 9; // C3892

 // Correct usage: the conditional operator returns an lvalue.
 ((i < 3) ? i : j) = 7;
}
```

> [!NOTE]
> В примерах этого раздела показано правильное и неправильное использование при неперегруженных операторах. Перегрузив операторы, можно преобразовать выражение, такое как `j * 4`, в значение lvalue.

Условия *lvalue* и *rvalue* часто используются при ссылке на ссылки на объекты. Дополнительные сведения о ссылках см. в разделе [декларатор ссылки Lvalue: &](../cpp/lvalue-reference-declarator-amp.md) и [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также

 [Основные понятия](../cpp/basic-concepts-cpp.md) [декларатор ссылки Lvalue: &](../cpp/lvalue-reference-declarator-amp.md) [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md)