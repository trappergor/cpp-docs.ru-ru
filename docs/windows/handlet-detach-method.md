---
title: Метод HandleT::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc11d6be992584adb1ce2075e73d080cc3a43f47
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569483"
---
# <a name="handletdetach-method"></a>Метод HandleT::Detach
Отсоединяет текущий **HandleT** объект из его базовый дескриптор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Базовый дескриптор.  
  
## <a name="remarks"></a>Примечания  
 После завершения операции текущего **HandleT** присваивается недопустимое состояние.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)