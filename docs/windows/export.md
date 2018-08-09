---
title: Экспорт | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: ad5f886c4d475cb51b370ae25549387f191ab4b6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653135"
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
  
 При экспорте неименованные **перечисления**s или **структуры**s, они будут имена, начинающиеся с **__unnamed *** x*, где *x* выполняется последовательно номер.  
  
 Определения типов, допустимых для экспорта: базовые типы, структуры, объединения, перечисления или введите идентификаторы.  См. в разделе [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) Дополнительные сведения.  
  
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
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   