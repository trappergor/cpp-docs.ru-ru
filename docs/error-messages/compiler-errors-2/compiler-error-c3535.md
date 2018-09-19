---
title: Ошибка компилятора C3535 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3535
dev_langs:
- C++
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 215fa52f892cb569b32335ca439811eb07b28dc7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094082"
---
# <a name="compiler-error-c3535"></a>Ошибка компилятора C3535

Невозможно вывести тип для «тип1» в «тип2»

Тип переменной, объявленной с `auto` ключевое слово не может быть выведен из типа выражения инициализации. Например, эта ошибка возникает, если выражение инициализации равно `void`, который не является типом.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что тип выражения инициализации не является `void`.

1. Убедитесь, что объявление не является указателем на базовый тип. Дополнительные сведения см. в разделе [фундаментальные типы](../../cpp/fundamental-types-cpp.md).

1. Убедитесь, что если объявление является указателем на тип, выражение инициализации является типом указателя.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3535, так как выражение инициализации для `void`.

```
// C3535a.cpp
// Compile with /Zc:auto
void f(){}
int main()
{
   auto x = f();   //C3535
   return 0;
}
```

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3535, поскольку оператор объявляет переменную `x` как указатель на выведенный тип, но тип инициализатора выражение double. Следовательно компилятор не может вывести тип переменной.

```
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3535, так как переменная `p` объявляет указатель на выведенный тип, но выражение инициализации не является типом указателя.

```
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[Фундаментальные типы](../../cpp/fundamental-types-cpp.md)