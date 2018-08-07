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
ms.openlocfilehash: 933fc1db2a890fedd9d725c49bbeb6c363e2f4c8
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569642"
---
# <a name="entry"></a>entry
Указывает экспортированной функции или константы в модуле, определяя точки входа в библиотеку DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ entry(  
   id  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
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