---
title: usesgetlasterror | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 399b9fbbcf4b449f5f91beaea89c403d120d0a21
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890279"
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
