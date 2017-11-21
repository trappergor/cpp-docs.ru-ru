---
title: "Метод DeferrableEventArgs::GetDeferral | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d43aa6d82f44965e8defda2af3e6455e86cba38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="deferrableeventargsgetdeferral-method"></a>Метод DeferrableEventArgs::GetDeferral
Возвращает ссылку на [отсрочки](http://go.microsoft.com/fwlink/?LinkId=526520) объект, который представляет отложенное событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>Параметры  
 `result`  
 Указатель, который будет ссылаться [отсрочки](http://go.microsoft.com/fwlink/?LinkId=526520) объекта после завершения вызова.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Пример кода см. в разделе [класс DeferrableEventArgs](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)