---
title: "usesgetlasterror | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05c74f1254230270654b3dc0b44f541e4fe9ef2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="usesgetlasterror"></a>usesgetlasterror
Сообщает вызывающего объекта, если возникает ошибка при вызове этой функции, затем вызывающий объект может затем вызвать `GetLastError` для получения кода ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Usesgetlasterror** языка C++ имеет ту же функциональность, что [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) языка MIDL.  
  
## <a name="example"></a>Пример  
 В разделе [idl_module](../windows/idl-module.md) примере образец демонстрирует использование **usesgetlasterror**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**модуль** атрибута|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
