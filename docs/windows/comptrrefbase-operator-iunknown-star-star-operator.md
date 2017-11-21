---
title: "Оператор ComPtrRefBase::operator IUnknown ** | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs: C++
helpviewer_keywords: operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3881dbec0af43f87ff3f880da71299efdf26c64a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)