---
title: "Метод AsyncBase::TryTransitionToError | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6da3d84e3e5e1ee0fd71da1cf59ec79497f81d35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasetrytransitiontoerror-method"></a>Метод AsyncBase::TryTransitionToError
Указывает, является ли указанный код ошибки можно изменить состояние Внутренняя ошибка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `error`  
 HRESULT ошибки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если внутренняя ошибка состояние было изменено; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Эта операция изменяет состояние ошибки только в том случае, если состояние ошибки уже имеет значение S_OK. Эта операция оказывает никакого влияния, если состояние ошибки уже ошибка, отменено, завершено или закрыт.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)