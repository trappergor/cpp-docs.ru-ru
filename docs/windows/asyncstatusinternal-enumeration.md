---
title: Перечисление AsyncStatusInternal | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 150169442aa68395b4dc8a4f4c74951e877f18f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal - перечисление
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Примечания  
 Задает сопоставление между внутренними перечислениями состояний асинхронных операций и **Windows::Foundation::AsyncStatus** перечисления.  
  
## <a name="members"></a>Участники  
 `_Created`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Created  
  
 `_Started`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Started  
  
 `_Completed`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Completed  
  
 `_Cancelled`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Cancelled  
  
 `_Error`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)