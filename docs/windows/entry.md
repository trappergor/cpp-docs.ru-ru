---
title: запись | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f644df2969954187aa4506d2cc1d04d140f88de3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642891"
---
# <a name="entry"></a>entry
Указывает экспортированной функции или константы в модуле, определяя точки входа в библиотеку DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ entry(  
   id  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 Идентификатор точки входа.  
  
## <a name="remarks"></a>Примечания  
 **Запись** атрибут C++ имеет ту же функциональность, что [запись](http://msdn.microsoft.com/library/windows/desktop/aa366815) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в примере [idl_module](../windows/idl-module.md) для пример использования **запись**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Атрибут `idl_module`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   