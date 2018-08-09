---
title: Метод AsyncBase::GetOnComplete | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnComplete
dev_langs:
- C++
helpviewer_keywords:
- GetOnComplete method
ms.assetid: f06ae02d-9a88-41d2-b749-bdc1a7ff8748
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ffe517b75df4e1cdd8172279c12256db940f0980
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647041"
---
# <a name="asyncbasegetoncomplete-method"></a>Метод AsyncBase::GetOnComplete
Копирует адрес текущего обработчика событий завершения в указанной переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(  
   GetOnComplete  
)(TComplete** completeHandler);  
```  
  
### <a name="parameters"></a>Параметры  
 *completeHandler*  
 Расположение, где хранится адрес текущего обработчика событий завершения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)