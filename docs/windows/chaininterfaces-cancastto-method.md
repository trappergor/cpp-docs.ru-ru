---
title: Метод ChainInterfaces::CanCastTo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2286c347fbd68f34fac807e80facca0a0286aa6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="chaininterfacescancastto-method"></a>Метод ChainInterfaces::CanCastTo
Указывает ли идентификатор интерфейса указанного может быть приведен к каждому специализации, определяемая параметрами шаблона не по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `ppv`  
 Указатель на идентификатор последнего интерфейс, который был приведен успешно.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` При успешном завершении всех операций приведения. в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)