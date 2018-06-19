---
title: Экспорт | Документы Microsoft
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
ms.openlocfilehash: 67b71639fc0b7d0039f5665d2cc187191ac14baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874607"
---
# <a name="export"></a>экспорт
В результате структуру данных помещается в IDL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[export]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Экспорт** языка C++ вызывает структуру данных помещается в IDL-файл и затем быть доступны в библиотеке типов в совместимых формате, который делает доступными для использования с любым языком.  
  
 Не удается применить **Экспорт** атрибута к классу, даже если класс имеет только открытые члены (эквивалент `struct`).  
  
 Если вы экспортируете неименованные `enum`s или `struct`s, они будут имена, начинающиеся с **__unnamed *** x*, где *x* — это последовательный номер.  
  
 Определения типов, допустимый для экспорта: базовые типы, структуры, объединения, перечисления, либо введите идентификаторы.  В разделе [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать **Экспорт** атрибута:  
  
```  
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
|**Применение**|**Объединение**, `typedef`, `enum`, `struct`, или `interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   
