---
title: Экспорт (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a636b7d4c943896bcd1e5e7b3580c2d3f7410fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791197"
---
# <a name="export"></a>экспорт

В результате структуру данных, должно быть помещено в IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[export]
```

## <a name="remarks"></a>Примечания

**Экспорт** C++ атрибут приводит к структуре данных помещается в IDL-файла и затем был доступен в библиотеке типов в виде совместимых, что делает ее доступной для использования с помощью любого языка.

Невозможно применить **Экспорт** атрибута к классу, даже если класс имеет только открытые члены (эквивалент **структуры**).

Если вы экспортируете неименованный **перечисления** или **структуры**, ему присваивается имя, которое начинается с **__unnamed**<em>x</em>, где *x* является последовательным номером.

Определения типов, допустимых для экспорта: базовые типы, структуры, объединения, перечисления или введите идентификаторы.  См. в разделе [typedef](/windows/desktop/Midl/typedef) Дополнительные сведения.

## <a name="example"></a>Пример

Ниже показано, как использовать **Экспорт** атрибут:

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
|**Применение**|**Объединение**, **typedef**, **перечисления**, **структуры**, или **интерфейса**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)  