---
title: Метод DeferrableEventArgs::GetDeferral | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2442894c5f7bd85eb94262e776294c1e52a19e01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="deferrableeventargsgetdeferral-method"></a>Метод DeferrableEventArgs::GetDeferral
Возвращает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>Параметры  
 `result`  
 Указатель, который будет ссылаться [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объекта после завершения вызова.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Пример кода см. в разделе [класс DeferrableEventArgs](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)