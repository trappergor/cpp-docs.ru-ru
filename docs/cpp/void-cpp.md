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
ms.openlocfilehash: 2de019f908942a58b232877fcd9eebc4689d8e22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187483"
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

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Встроенные типы](../cpp/fundamental-types-cpp.md)
