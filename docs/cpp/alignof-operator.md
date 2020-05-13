---
title: Оператор __alignof
ms.date: 12/17/2018
f1_keywords:
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 6bddce29dd97d965303a58cc72aa97dfe8cbd8d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181542"
---
# <a name="__alignof-operator"></a>Оператор __alignof

В c++ 11 появился оператор **alignof** , возвращающий выравнивание указанного типа в байтах. Для обеспечения максимальной переносимости кода следует использовать оператор alignof вместо оператора __alignof, тесно связанного с системами Майкрософт.

**Блок, относящийся только к системам Microsoft**

Возвращает значение типа `size_t`, которое является требованием выравнивания для типа.

## <a name="syntax"></a>Синтаксис

```cpp
  __alignof( type )
```

## <a name="remarks"></a>Remarks

Пример:

|Выражение|Значение|
|----------------|-----------|
|**__alignof (char)**|1|
|**__alignof (короткий)**|2|
|**__alignof (int)**|4|
|**__alignof (\__int64)**|8|
|**__alignof (float)**|4|
|**__alignof (Double)**|8|
|**__alignof (char\*)**|4|

Значение **__alignof** равно значению для `sizeof` базовых типов. Однако рассмотрим следующий пример.

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

В этом случае **__alignof** значение является требованием выравнивания для самого крупного элемента в структуре.

Аналогичным образов, в

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)` равно `32`.

Одним из способов использования **__alignof** является параметр одной из собственных подпрограмм выделения памяти. Например, в следующей определенной структуре `S` можно вызвать подпрограмму выделения памяти с именем `aligned_malloc` для выделения памяти на определенной границе выравнивания.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

Для совместимости с предыдущими версиями **_alignof** является синонимом для **__alignof** , если только не указан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

Дополнительные сведения об изменении выравнивания см. в следующих разделах.

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/x64-software-conventions.md#examples-of-structure-alignment) (только для x64)

Дополнительные сведения о различиях в выравнивании в коде для 32- (x86) и 64-разрядных (x64) сред см. в статье

- [Конфликты с 32-разрядным (x86) компилятором](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
