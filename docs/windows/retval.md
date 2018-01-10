---
title: "retval | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.retval
dev_langs: C++
helpviewer_keywords: retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7aa0cf8dd9767f603807ee18e23fe02d3446c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="retval"></a>retval
Назначает параметр, который получает возвращаемое значение члена.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Retval** языка C++ имеет ту же функциональность, что [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) языка MIDL.  
  
 **retval** должны располагаться на последний аргумент в объявлении функции.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [привязываемых](../windows/bindable.md) для приведен пример использования **retval**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**out**|  
|**Недопустимые атрибуты**|**in**|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
