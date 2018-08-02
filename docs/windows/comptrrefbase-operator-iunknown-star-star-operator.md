---
title: Оператор ComPtrRefBase::operator IUnknown ** | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2ec20dca7bb0a37adae576a8b5a9adfad027b21
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465819"
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>Оператор ComPtrRefBase::operator IUnknown**
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
operator IUnknown**() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член в указатель к a указатель to `IUnknown` интерфейс.  
  
 Ошибка создается в том случае, если текущий **ComPtrRefBase** не является производным от `IUnknown`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrrefbase-класс](../windows/comptrrefbase-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)