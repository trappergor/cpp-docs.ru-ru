---
title: "Сокеты Windows: Наследование от классов сокета | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0152afbafe7c4756bebd87f931b9a6b6f4e31269
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Сокеты Windows. Наследование от классов сокета
В этой статье описываются функциональные возможности, которые можно получить собственного класса, производного от одного из классов сокетов.  
  
 Можно создавать производные классы сокета либо [CAsyncSocket](../mfc/reference/casyncsocket-class.md) или [CSocket](../mfc/reference/csocket-class.md) для добавления собственных функций. В частности эти классы, введите номер виртуальных функций-членов, можно переопределить. Эти функции включают [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), и [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Функции можно переопределять в классе производном сокета позволяет воспользоваться преимуществами уведомления, которые они предоставляют при возникновении событий сети. Платформа вызывает эти функции обратного вызова уведомления об изменениях сокета важные события, например, получение данных, можно начать чтение. Дополнительные сведения о функции уведомления см. в разделе [Windows Sockets: уведомления сокетов](../mfc/windows-sockets-socket-notifications.md).  
  
 Кроме того, класс `CSocket` предоставляет [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) функция-член (расширенная переопределяемый). MFC вызывает эту функцию, пока сокет обработка сообщений на основе Windows. Можно переопределить `OnMessagePending` для поиска определенных сообщений из Windows и отвечать на них.  
  
 Версия по умолчанию `OnMessagePending` указан в классе `CSocket` проверяет очередь сообщений для `WM_PAINT` сообщений при ожидании завершения блокирующий вызов. Он отправляет сообщения рисования для повышения качества изображения. Помимо образом осмысленное, это иллюстрирует один из способов может переопределить функцию самостоятельно. Например, рассмотрите возможность использования `OnMessagePending` для следующих задач. Предположим, что отображения немодального диалогового окна во время ожидания завершения транзакции сети. Диалоговое окно содержит кнопку "Отмена", пользователь может использовать для отмены блокировки транзакций, которые слишком долго. Ваш `OnMessagePending` переопределения может выдавать сообщения, связанные с этой немодального диалогового.  
  
 В вашей `OnMessagePending` переопределения, возвращать либо **TRUE** или возврат из вызова версии базового класса `OnMessagePending`. Вызовите версию базового класса, если он выполняет работу, которую следует сделать.  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Сокеты Windows. Блокировка](../mfc/windows-sockets-blocking.md)  
  
-   [Сокеты Windows. Порядок байтов](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Сокеты Windows. Преобразование строк](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)

