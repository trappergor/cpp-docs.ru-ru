---
title: "Метод HandleT::Detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25ee0e3ea826d77795bbdfafda780071d7a817a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handletdetach-method"></a>Метод HandleT::Detach
Отсоединяет текущий объект HandleT из его базового дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Базовый дескриптор.  
  
## <a name="remarks"></a>Примечания  
 По завершении этой операции текущего объекта HandleT присваивается недопустимое состояние.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)