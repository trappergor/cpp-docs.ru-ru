---
title: "Глобальные функции обработки событий | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlbase/ATL::AtlWaitWithMessageLoop
dev_langs: C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 747704bb271c294728832c8ee8108da458c739ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="event-handling-global-functions"></a>Глобальные функции для обработки событий
Эта функция предоставляет обработчик событий.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Ожидает объекта сигнала, в то же время диспетчеризацию сообщений о необходимости.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 Ожидает объекта, о котором требуется сигнализировать; во время ожидания производит требуемую диспетчеризацию сообщений.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Параметры  
 `hEvent`  
 [in] Дескриптор объекта для ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при оповещении объекта.  
  
### <a name="remarks"></a>Примечания  
 Это полезно, если нужно дождаться события объекта и узнавать о ее повторение, но разрешить окна сообщения для отправки во время ожидания.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
