---
title: Ошибка компилятора C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: 8db1ba622a0c83a7f2a6421d79ff5853cbc4d9a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555564"
---
# <a name="compiler-error-c3101"></a>Ошибка компилятора C3101

Недопустимое выражение для аргумента атрибута с именем «field»

При инициализации является аргументом именованного атрибута, значение должно быть константой времени компиляции.

Дополнительные сведения об атрибутах см. в разделе [определяемые пользователем атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3101.

```
// C3101.cpp
// compile with: /clr /c
ref class AAttribute : System::Attribute {
public:
   int Field;
};

extern int i;

[assembly:A(Field = i)];   // C3101
[assembly:A(Field = 0)];   // OK
```