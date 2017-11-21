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
ms.openlocfilehash: 092aa684cace186e3aa5ad443e6f419f10d68160
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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