---
title: Метод AsyncBase::get_Id | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Id
dev_langs:
- C++
helpviewer_keywords:
- get_Id method
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab02da2dcae788e5eb4b1db15508d2f272ec546a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651562"
---
# <a name="asyncbasegetid-method"></a>Метод AsyncBase::get_Id
Извлекает дескриптор асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 Расположение, где будет храниться дескриптор.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализует `IAsyncInfo::get_Id`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)