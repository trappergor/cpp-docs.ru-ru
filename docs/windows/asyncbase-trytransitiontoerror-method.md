---
title: Метод AsyncBase::TryTransitionToError | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc677304ae7ab61e6726366869e85f731cd92484
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463211"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>Метод AsyncBase::TryTransitionToError
Указывает, является ли указанный код ошибки можно изменить внутреннее состояние ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *Ошибка*  
 Ошибка HRESULT.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** если внутреннее состояние ошибки было изменено; в противном случае — значение **false**.  
  
## <a name="remarks"></a>Примечания  
 Эта операция изменяет состояние ошибки только в том случае, если состояние ошибки уже имеет значение S_OK. Эта операция не оказывает влияния Если состояние ошибки не ошибка, отменено, завершено или закрыт.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)