---
title: "Оператор ComPtrRefBase::operator IUnknown ** | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04eaa2992c74b4cb46954ac73aa7b5a8ae735f82
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>Оператор ComPtrRefBase::operator IUnknown**
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
operator IUnknown**() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член к указатель в a указатель интерфейса IUnknown.  
  
 Если текущий ComPtrRefBase не является производным от IUnknown, выдается ошибка.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>См. также  
 [Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)