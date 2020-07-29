---
title: Export (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: ae7c426466bfaf4a325ba1cafe30c8ca74f8ef95
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228080"
---
# <a name="export"></a>экспорт

Приводит к размещению структуры данных в IDL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[export]
```

## <a name="remarks"></a>Remarks

**`[export]`** Атрибут C++ заставляет разместить структуру данных в IDL-файле и затем быть доступной в библиотеке типов в двоичном совместимом формате, который делает его доступным для использования с любым языком.

Атрибут нельзя применить **`[export]`** к классу, даже если он содержит только открытые члены (эквивалент типа **`struct`** ).

Если вы экспортируете безымянное имя **`enum`** или **`struct`** , ему присваивается имя, начинающееся с **__unnamed**<em>x</em>, где *x* — это порядковый номер.

Определение типов, допустимых для экспорта, — это базовые типы, структуры, объединения, перечисления или идентификаторы типов.  [`typedef`](/windows/win32/Midl/typedef)Дополнительные сведения см. в разделе.

## <a name="example"></a>Пример

В следующем коде показано, как использовать **`[export]`** атрибут:

```cpp
// cpp_attr_ref_export.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`union`**,,, **`typedef`** **`enum`** **`struct`** или**`interface`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также статью

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)
