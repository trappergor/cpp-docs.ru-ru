---
title: "Конструктор RoInitializeWrapper::RoInitializeWrapper | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs: C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5af6ca55445a5b8ed17a685cc0a81e8058a0eb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>Конструктор RoInitializeWrapper::RoInitializeWrapper
Инициализирует новый экземпляр класса RoInitializeWrapper.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 Одно из перечислений RO_INIT_TYPE, которые задает поддержку, предоставляемые средой выполнения Windows.  
  
## <a name="remarks"></a>Примечания  
 Класс RoInitializeWrapper вызывает Windows::Foundation::Initialize (*флаги*).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)