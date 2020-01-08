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
ms.openlocfilehash: 8a2c74e9ace77e38587209a0ad6fdc03b07cc3ad
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301760"
---
# <a name="void-c"></a>void (C++)

При использовании в качестве возвращаемого типа функции ключевое слово **void** указывает, что функция не возвращает значение. При использовании для списка параметров функции **void** указывает, что функция не принимает параметров. При использовании в объявлении указателя **void** указывает, что указатель является универсальным.

Если тип указателя — **void\*** , указатель может указывать на любую переменную, которая не объявлена с ключевым словом **const** или **volatile** . **Пустой указатель\*** не может быть разыменован, если он не приведен к другому типу. Указатель **типа void\*** может быть преобразован в любой другой тип указателя данных.

Указатель **void** может указывать на функцию, но не на член класса в C++.

Нельзя объявить переменную типа **void**.

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

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Встроенные типы](../cpp/fundamental-types-cpp.md)