---
title: bool (C++)
ms.date: 11/04/2016
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
ms.openlocfilehash: db246cda79c778f37c5afbfda4a68c191c474e12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190499"
---
# <a name="bool-c"></a>bool (C++)

Это ключевое слово является встроенным типом. Переменная этого типа может иметь значения [true](../cpp/true-cpp.md) и [false](../cpp/false-cpp.md). Условные выражения имеют тип **bool** и поэтому имеют значения типа **bool**. Например, `i!=0` теперь имеет значение TRUE или FALSE в зависимости от значения `i`.

**Visual Studio 2017 версии 15,3 и более поздних версий** (доступно с [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): операнд постфиксного или инкрементного оператора или оператор декремента не может иметь тип **bool**. Иными словами, при присвоении переменной `b` типа **bool**эти выражения больше не разрешаются:

```cpp
    b++;
    ++b;
    b--;
    --b;
```

Значения TRUE и FALSE имеют следующую связь:

```cpp
!false == true
!true == false
```

В следующем операторе

```cpp
if (condexpr1) statement1;
```

Если `condexpr1` имеет значение TRUE, `statement1` всегда выполняется; Если `condexpr1` имеет значение FALSE, `statement1` никогда не выполняется.

Если постфиксный или префиксный оператор **++** применяется к переменной типа **bool**, переменной присваивается значение true.
**Visual Studio 2017 версии 15,3 и более поздних версий**: operator + + для **bool** был удален из языка и больше не поддерживается.

Постфиксный или префиксный оператор **--** не может применяться к переменной этого типа.

Тип **bool** участвует в целочисленных повышениях. R-значение типа **bool** может быть преобразовано в r-значение типа **int**, при этом false становится нулевым, а значение true — на единицу. В качестве отдельного типа **логическое** значение участвует в разрешении перегрузки.

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Встроенные типы](../cpp/fundamental-types-cpp.md)
