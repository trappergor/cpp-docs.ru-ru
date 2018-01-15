---
title: "Метод EventTargetArray::Begin | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray::Begin
dev_langs: C++
helpviewer_keywords: Begin method
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96bf73de31733fb10eba0156de90b5d0f196b4ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarraybegin-method"></a>Метод EventTargetArray::Begin
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ComPtr<IUnknown>* Begin();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адрес первого элемента во внутреннем массиве обработчиков событий.  
  
## <a name="remarks"></a>Примечания  
 Получает адрес первого элемента во внутреннем массиве обработчиков событий.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Eventtargetarray-класс](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)