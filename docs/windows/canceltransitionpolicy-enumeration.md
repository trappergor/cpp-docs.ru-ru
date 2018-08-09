---
title: Перечисление CancelTransitionPolicy | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd203ee0413b60bc7aa713e7923fd4d69bde665e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642962"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy - перечисление
Показывает, как попытка перехода асинхронной операции к окончательному состоянию завершения или ошибки должна происходить с учетом запрошенного клиентом состояния отмены.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum CancelTransitionPolicy;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
|----------|-----------------|  
|`RemainCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, это означает, что данный элемент остается в отмененном состоянии, в отличие от перехода к окончательному состоянию завершения или ошибки.|  
|`TransitionFromCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, это означает, что состояние должно перейти из данного состояния отмены в окончательное состояние завершения или ошибки, как определено вызовом, который использует этот флажок.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)