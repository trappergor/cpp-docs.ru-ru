---
title: Ошибка компилятора C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 85381b237480b86b59c33f02601a1b9dc644a5a4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761534"
---
# <a name="compiler-error-c3539"></a>Ошибка компилятора C3539

"тип": аргумент шаблона не может быть типом, содержащим "Auto"

Указанный тип аргумента шаблона не может содержать использование ключевого слова `auto`.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не указывайте аргумент шаблона с ключевым словом `auto`.

## <a name="example"></a>Пример

В следующем примере выдается C3539.

```cpp
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)
