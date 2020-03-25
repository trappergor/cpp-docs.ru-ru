---
title: Export (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 6264db037069f5fc6b858bdd466ce6c68b814a84
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167048"
---
# <a name="export"></a>экспорт

Приводит к размещению структуры данных в IDL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[export]
```

## <a name="remarks"></a>Remarks

Атрибут **Export** C++ заставляет разместить структуру данных в IDL-файле и затем быть доступной в библиотеке типов в двоичном совместимом формате, который делает его доступным для использования с любым языком.

Атрибут **Export** нельзя применить к классу, даже если класс содержит только открытые члены (эквивалент **структуры**).

При экспорте безымянного **перечисления** или **структуры**ему присваивается имя, начинающееся с **__unnamed**<em>x</em>, где *x* — это порядковый номер.

Определение типов, допустимых для экспорта, — это базовые типы, структуры, объединения, перечисления или идентификаторы типов.  Дополнительные сведения см. в разделе [typedef](/windows/win32/Midl/typedef) .

## <a name="example"></a>Пример

В следующем коде показано, как использовать атрибут **Export** :

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
|**Применение**|**Union**, **typedef**, **перечисление**, **Структура**или **интерфейс**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)
