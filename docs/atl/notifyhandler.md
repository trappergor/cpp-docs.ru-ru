---
title: NotifyHandler | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74fbdd99c162b4362339d8c1b45ddc281d30eeee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="notifyhandler"></a>NotifyHandler
Имя функции, определяемому третий параметр `NOTIFY_HANDLER` макрос в схему сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
    LRESULT 
    NotifyHandler 
 (
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Параметры  
 `idCtrl`  
 Идентификатор элемента управления, отправляющего сообщения.  
  
 *pnmh*  
 Адрес [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) структура, содержащая код уведомления и Дополнительные сведения. Для некоторых сообщений уведомлений, этот параметр указывает на более крупной структуры, который имеет **NMHDR** структуру, что ее первого элемента.  
  
 `bHandled`  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед *NotifyHandler* вызывается. Если *NotifyHandler* не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения. 0 в случае успеха.  
  
## <a name="remarks"></a>Примечания  
 Пример использования этого обработчика сообщений в схеме сообщений см. в разделе [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)   
 [Схемы сообщений](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

