---
title: Метод AsyncBase::GetOnProgress | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs:
- C++
helpviewer_keywords:
- GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9446c94039db0ff81826e77d71a2a9539be4b276
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643151"
---
# <a name="asyncbasegetonprogress-method"></a>Метод AsyncBase::GetOnProgress
Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
### <a name="parameters"></a>Параметры  
 *progressHandler*  
 Расположение, в котором сохраняется адрес текущего обработчика событий процесса выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)