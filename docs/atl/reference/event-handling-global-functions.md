---
title: Глобальные функции обработки событий | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85babf3155fdc94dafd5d62c2e67401e5add3663
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884003"
---
# <a name="event-handling-global-functions"></a>Глобальные функции для обработки событий
Эта функция предоставляет обработчик событий.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Ожидает объекта сигнала, в то же время диспетчеризации сообщений окна, при необходимости.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop  
 Ожидает объекта, о котором требуется сигнализировать; во время ожидания производит требуемую диспетчеризацию сообщений.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Параметры  
 *hEvent*  
 [in] Дескриптор объекта ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если объект оповещении.  
  
### <a name="remarks"></a>Примечания  
 Это полезно в том случае, если вы хотите ждать события объекта, и получать оповещения о них происходит, но разрешить окно сообщения для отправки во время ожидания.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
