---
title: MessageHandler | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dcd02396fa76e9e68fce628783fb17bc6adab36e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848406"
---
# <a name="messagehandler"></a>MessageHandler
`MessageHandler` — имя функции, заданных в качестве второго параметра макроса MESSAGE_HANDLER в схему сообщения.  
  
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
 *uMsg*  
 Задает сообщение.  
  
 *wParam*  
 Дополнительные сведения, относящиеся к сообщению.  
  
 *lParam*  
 Дополнительные сведения, относящиеся к сообщению.  
  
 *bHandled*  
 Карта наборов сообщений *bHandled* значение TRUE перед `MessageHandler` вызывается. Если `MessageHandler` не полностью обрабатывает сообщение, она должна задать *bHandled* значение false, чтобы указать, должна дальнейшей обработки сообщения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения. 0 в случае успеха.  
  
## <a name="remarks"></a>Примечания  
 Пример использования этого обработчика сообщений в схеме сообщений, см. в разделе [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)   
 [Схемы сообщений](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

