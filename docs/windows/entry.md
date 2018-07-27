---
title: запись | Документы Microsoft
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
ms.openlocfilehash: db90390be5313ddbea1103105f47b55fe9e23d62
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872319"
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
 `id`  
 Идентификатор точки входа.  
  
## <a name="remarks"></a>Примечания  
 **Входа** языка C++ имеет ту же функциональность, что [входа](http://msdn.microsoft.com/library/windows/desktop/aa366815) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [idl_module](../windows/idl-module.md) для пример использования **входа**.  
  
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
