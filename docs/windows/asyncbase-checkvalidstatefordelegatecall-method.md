---
title: Метод AsyncBase::CheckValidStateForDelegateCall | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForDelegateCall method
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a03f0dcb8f6d35c1d5fc8aec5bf1cc899d575861
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653076"
---
# <a name="asyncbasecheckvalidstatefordelegatecall-method"></a>Метод AsyncBase::CheckValidStateForDelegateCall
Проверяет, является ли делегат свойства можно изменить в текущем состоянии асинхронной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если делегат свойства можно изменить; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)