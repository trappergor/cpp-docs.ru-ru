---
title: "Глобальные функции обработки событий | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4bf2a8b0211361f5d5d2bf0f996e978638631116
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="event-handling-global-functions"></a>Глобальные функции обработки событий
Эта функция предоставляет обработчик событий.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Ожидает объекта сигнала, в то же время диспетчеризацию сообщений о необходимости.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 Ожидает объекта, о котором требуется сигнализировать; во время ожидания производит требуемую диспетчеризацию сообщений.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Параметры  
 `hEvent`  
 [in] Дескриптор объекта ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при оповещении объекта.  
  
### <a name="remarks"></a>Примечания  
 Это полезно, если требуется ожидать события объекта произойти и получать уведомления об ее повторение, но разрешить оконные сообщения для отправки во время ожидания.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

