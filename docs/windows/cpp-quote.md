---
title: cpp_quote | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 21f986e227e9daca58731d03c40d6dae5b0c0a80
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653044"
---
# <a name="cppquote"></a>cpp_quote
Выдает заданную строку, без знаков кавычек в созданного IDL-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ cpp_quote(  
   "statement"  
) ];  
```  
  
### <a name="parameters"></a>Параметры  
 *statement*  
 Инструкцию "C".  
  
## <a name="remarks"></a>Примечания  
 **Cpp_quote** C++ атрибут полезен, если вы хотите поместить директиву препроцессора в IDL-файле.  
  
 Можно также использовать **cpp_quote** и формирования h-файле в процессе компиляции MIDL. Например если файл заголовка C++, который использует атрибуты C++ IDL, но не может использовать этот файл для некоторых задач, после этого можно скомпилировать его, чтобы создать файл созданные MIDL .h, который можно использовать.  
  
 **Cpp_quote** атрибут имеет ту же функциональность, что [cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [двойного](../windows/dual.md) пример использования способы использования **cpp_quote**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   