---
title: Export (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 771bfdfe4eab2acf31e97a606795066e8938a8a1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501607"
---
# <a name="export"></a>экспорт

Приводит к размещению структуры данных в IDL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[export]
```

## <a name="remarks"></a>Примечания

Атрибут **Export** C++ заставляет разместить структуру данных в IDL-файле и затем быть доступной в библиотеке типов в двоичном совместимом формате, который делает его доступным для использования с любым языком.

Атрибут **Export** нельзя применить к классу, даже если класс содержит только открытые члены (эквивалент **структуры**).

При экспорте безымянного **перечисления** или **структуры**ему присваивается имя, которое начинается с **__unnamed**<em>x</em>, где *x* — это порядковый номер.

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
|**Относится к**|**Union**, **typedef**,перечисление, **Структура**или **интерфейс**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)