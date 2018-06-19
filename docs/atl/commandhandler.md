---
title: CommandHandler | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27f5585ec334a4179b76579c5216c8c30013ca97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355142"
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler` является функция, определяемая третий параметр `COMMAND_HANDLER` макрос в схему сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
    LRESULT 
    CommandHandler 
 (
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Параметры  
 `wNotifyCode`  
 Код уведомления.  
  
 *wID*  
 Идентификатор элемента меню, элемент управления или сочетаний клавиш.  
  
 *hWndCtl*  
 Дескриптор окна элемента управления.  
  
 `bHandled`  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `CommandHandler` вызывается. Если `CommandHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения. 0 в случае успеха.  
  
## <a name="remarks"></a>Примечания  
 Пример использования этого обработчика сообщений в схеме сообщений см. в разделе [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)   
 [Схемы сообщений](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

