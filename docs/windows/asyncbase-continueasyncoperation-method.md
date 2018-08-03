---
title: Метод AsyncBase::ContinueAsyncOperation | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7b5d2b10b571a3517beab98eaa839d5c7fd86c2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460837"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>Метод AsyncBase::ContinueAsyncOperation
Определяет, должны продолжать обработку асинхронной операции или следует остановить.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если текущее состояние асинхронной операции *работы*, который означает, что операция должна продолжаться. В противном случае **false**, который означает, что операция следует остановить.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)