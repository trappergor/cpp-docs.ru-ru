---
title: Оператор ComPtrRef::operator void ** | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs:
- C++
helpviewer_keywords:
- operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbe9f077fd0d80a831d319660be26090ad5411f6
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463857"
---
# <a name="comptrrefoperator-void-operator"></a>ComPtrRef::operator void\* \* оператор
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
operator void**() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Удаляет текущий **ComPtrRef** объекта, приведение указателя на интерфейс, который был представлен **ComPtrRef** объекта как указатель к указатель to **void**, а затем Возвращает указатель приведения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrref-класс](../windows/comptrref-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)