---
title: "Метод AsyncBase::get_Id | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Id
dev_langs:
- C++
helpviewer_keywords:
- get_Id method
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3655a82c3c7fee8ed9fe3361231f94a39f65a7d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasegetid-method"></a>Метод AsyncBase::get_Id
Извлекает дескриптор асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
#### <a name="parameters"></a>Параметры  
 `id`  
 Расположение, где будет храниться дескриптор.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализует IAsyncInfo::get_Id.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)