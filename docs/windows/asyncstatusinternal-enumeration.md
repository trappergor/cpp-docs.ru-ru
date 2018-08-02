---
title: Asyncstatusinternal-перечисление | Документация Майкрософт
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
ms.openlocfilehash: a68189c461453dc72585ff4034df5ba69bb41bd5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464880"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal - перечисление
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Примечания  
 Задает сопоставление между внутренними перечислениями состояний асинхронных операций и перечислением `Windows::Foundation::AsyncStatus`.  
  
## <a name="members"></a>Участники  
 *_Created*  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Created  
  
 *_Started*  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Started  
  
 *_Completed*  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Completed  
  
 *_Cancelled*  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Cancelled  
  
 *_Сведения*  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)