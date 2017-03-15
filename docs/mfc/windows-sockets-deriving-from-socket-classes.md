---
title: "Сокеты Windows. Наследование от классов сокета | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "производные классы, из классов сокетов"
  - "сокеты [C++], наследование из классов сокетов"
  - "Сокеты Windows [C++], наследование из классов сокетов"
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Сокеты Windows. Наследование от классов сокета
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описываются некоторые из функций можно увеличить собственный класс, производный от одного из классов socket.  
  
 Можно создавать производные классы из собственных socket [CAsyncSocket](../Topic/CAsyncSocket%20Class.md) или [CSocket](../mfc/reference/csocket-class.md) для добавления собственной функции.  В частности, эти классы предоставляют несколько виртуальных функции\-члена, можно переопределить.  Эти функции включают [OnReceive](../Topic/CAsyncSocket::OnReceive.md), [OnSend](../Topic/CAsyncSocket::OnSend.md), [OnAccept](../Topic/CAsyncSocket::OnAccept.md), [OnConnect](../Topic/CAsyncSocket::OnConnect.md) и [OnClose](../Topic/CAsyncSocket::OnClose.md).  Можно переопределить функции в производном классе socket для использования уведомлений о событиях, сети предоставляет их возникновения.  Платформа вызывает эти функции обратного вызова уведомления, чтобы сообщить о важных событий сокета, например отправку данных данных, можно начать чтение.  Дополнительные сведения о функции уведомления см. в разделе [Windows SSL. Уведомления сокета](../Topic/Windows%20Sockets:%20Socket%20Notifications.md).  
  
 Кроме того, предоставляет `CSocket` класса функцию\-член [OnMessagePending](../Topic/CSocket::OnMessagePending.md) \(дополнительно переопределяемый метод\).  MFC вызывает данную функцию, сокет нагнетает на базе Windows сообщения.  Можно переопределить `OnMessagePending` для поиска конкретных сообщения от Windows и реагировать на них.  
  
 Версия по умолчанию `OnMessagePending` поставила в классе `CSocket` проверяет очередь сообщений для сообщений `WM_PAINT` во время ожидания блокирующий вызов для выполнения.  Она отправляет сообщения рисования, чтобы повысить качество отображения.  Приложение не имеет полезной, данный пример демонстрирует один из способов самостоятельно могут переопределить функцию.  Другой пример, можно использовать `OnMessagePending` для следующей задачи.  Предположим, что отображается безрежимное диалоговое окно во время ожидания транзакции сети для выполнения.  Диалоговое окно содержит Отмену, пользователь может использоваться для отмены блокирующие транзакции, которые слишком длинное.  Переопределенный `OnMessagePending` может отказать сообщениям, связанные с этим безрежимное диалоговое окно.  
  
 В переопределении `OnMessagePending`, возвращает **TRUE** или возврата из вызова версии базового класса `OnMessagePending`.  Вызовите версию базового класса, если она выполняет работу, при этом должны выполняться.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Windows SSL. С помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows SSL. С помощью класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows SSL. Блокировка](../Topic/Windows%20Sockets:%20Blocking.md)  
  
-   [Windows SSL. Порядок байтов](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows SSL. Преобразования строк](../mfc/windows-sockets-converting-strings.md)  
  
## См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)