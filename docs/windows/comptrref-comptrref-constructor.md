---
title: Конструктор ComPtrRef::ComPtrRef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24844588a18f269ee6f3a19286e6755b11b1c6bf
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463636"
---
# <a name="comptrrefcomptrref-constructor"></a>Конструктор ComPtrRef::ComPtrRef
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *ptr*  
 Базовое значение другого **ComPtrRef** объекта.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса **ComPtrRef** класс из заданного указателя в другой **ComPtrRef** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrref-класс](../windows/comptrref-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)