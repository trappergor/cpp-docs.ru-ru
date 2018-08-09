---
title: usesgetlasterror | Документация Майкрософт
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
ms.openlocfilehash: 011cf954a0b111e46afcaf6e55a54914075864db
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014566"
---
# <a name="usesgetlasterror"></a>usesgetlasterror
Вызывающий объект о том, есть ли ошибки при вызове этой функции, затем вызывающий объект затем можно вызвать `GetLastError` для получения кода ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[usesgetlasterror]  
```  
  
## <a name="remarks"></a>Примечания  
 **Usesgetlasterror** атрибут C++ имеет ту же функциональность, что [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 См. в разделе [idl_module](../windows/idl-module.md) примере образец демонстрирует использование **usesgetlasterror**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**модуль** атрибут|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   