---
title: "HandleT::operator =-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68afd6b2a0a1c17cd032d6cea84aefde8c368204
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handletoperator-operator"></a>Оператор HandleT::operator=
Перемещение текущего объекта HandleT значение указанного объекта HandleT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Ссылка rvalue на дескриптор.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект HandleT.  
  
## <a name="remarks"></a>Примечания  
 Эта операция делает недействительными объекта HandleT, заданного параметром `h`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)