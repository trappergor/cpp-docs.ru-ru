---
title: "MessageHandler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MessageHandler
dev_langs: C++
helpviewer_keywords: MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5a09439cf47c695af0d3b7d6c7724cffcb9ccb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="messagehandler"></a>MessageHandler
**MessageHandler** называется функция, определяемая вторым параметром `MESSAGE_HANDLER` макрос в схему сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
    LRESULT 
    MessageHandler 
 (
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Параметры  
 `uMsg`  
 Задает сообщение.  
  
 `wParam`  
 Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 Дополнительные сведения для конкретного сообщения.  
  
 `bHandled`  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `MessageHandler` вызывается. Если `MessageHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения. 0 в случае успеха.  
  
## <a name="remarks"></a>Примечания  
 Пример использования этого обработчика сообщений в схеме сообщений см. в разделе [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)   
 [Схемы сообщений](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

