---
title: Ошибка компилятора C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: d39afc548010df95bdf31b2c7708bc4fa0310bcd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779239"
---
# <a name="compiler-error-c3101"></a>Ошибка компилятора C3101

Недопустимое выражение для аргумента атрибута с именем «field»

При инициализации является аргументом именованного атрибута, значение должно быть константой времени компиляции.

Дополнительные сведения об атрибутах см. в разделе [определяемые пользователем атрибуты](../../extensions/user-defined-attributes-cpp-component-extensions.md).

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