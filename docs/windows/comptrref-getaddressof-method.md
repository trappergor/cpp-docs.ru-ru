---
title: Метод ComPtrRef::GetAddressOf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 435b853268d1fe8c324d217d1ad14f71e4b5a295
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462941"
---
# <a name="comptrrefgetaddressof-method"></a>Метод ComPtrRef::GetAddressOf
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InterfaceType* const * GetAddressOf() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адрес указателя на интерфейс, представленный текущим **ComPtrRef** объекта.  
  
## <a name="remarks"></a>Примечания  
 Извлекает адрес указателя на интерфейс, представленный текущим **ComPtrRef** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrref-класс](../windows/comptrref-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)