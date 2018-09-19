---
title: оператор __alignof | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs:
- C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffea0fdf40f7ef794563849f97b0b68631b9734e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099789"
---
# <a name="alignof-operator"></a>Оператор __alignof

C ++ 11 доступны **alignof** оператор, возвращающий выравнивание, в байтах указанного типа. Для обеспечения максимальной переносимости кода следует использовать оператор alignof вместо оператора __alignof, тесно связанного с системами Майкрософт.

**Блок, относящийся только к системам Microsoft**

Возвращает значение типа `size_t` то есть требование к выравниванию типа.

## <a name="syntax"></a>Синтаксис

```cpp
  __alignof( type )
```

## <a name="remarks"></a>Примечания

Пример:

|Выражение|Значение|
|----------------|-----------|
|**__alignof (char)**|1|
|**__alignof (short)**|2|
|**__alignof (int)**|4|
|**__alignof ( \__int64)**|8|
|**__alignof (float)**|4|
|**__alignof (double)**|8|
|**__alignof (char\* )**|4|

**__Alignof** значение совпадает со значением значение `sizeof` для основных типов. Однако рассмотрим следующий пример.

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

В этом случае **__alignof** значение является требованием к выравниванию наибольшего элемента в структуре.

Аналогичным образов, в

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)` равно `32`.

Один вариант использования **__alignof** бы в качестве параметра один из собственных процедур выделения памяти. Например, в следующей определенной структуре `S` можно вызвать подпрограмму выделения памяти с именем `aligned_malloc` для выделения памяти на определенной границе выравнивания.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

Дополнительные сведения об изменении выравнивания см. в следующих разделах.

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md) (x64 конкретных)

Дополнительные сведения о различиях в выравнивании в коде для 32- (x86) и 64-разрядных (x64) сред см. в статье

- [Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)