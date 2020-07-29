---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: fddfc2e3295552414a00692006ab12725dc07d52
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213116"
---
# <a name="void-c"></a>void (C++)

При использовании в качестве возвращаемого типа функции **`void`** ключевое слово указывает, что функция не возвращает значение. При использовании для списка параметров функции **`void`** указывает, что функция не принимает параметров. При использовании в объявлении указателя **`void`** указывает, что указатель является универсальным.

Если тип указателя — **void \* **, указатель может указывать на любую переменную, которая не объявлена с **`const`** **`volatile`** ключевым словом или. Указатель **void \* ** не может быть разыменован, если он не приведен к другому типу. Указатель **void \* ** можно преобразовать в любой другой тип указателя данных.

**`void`** Указатель может указывать на функцию, но не на член класса в C++.

Нельзя объявить переменную типа **`void`** .

## <a name="example"></a>Пример

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Встроенные типы](../cpp/fundamental-types-cpp.md)
