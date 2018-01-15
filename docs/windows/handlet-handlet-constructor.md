---
title: "Конструктор HandleT::HandleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs: C++
helpviewer_keywords: HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b72db4fb44191340b71c8bff26018221650ae34b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handlethandlet-constructor"></a>Конструктор HandleT::HandleT
Инициализирует новый экземпляр класса HandleT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Дескриптор.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует объект HandleT, не является допустимым дескриптором для объекта. Второй конструктор создает новый объект HandleT из параметра `h`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)