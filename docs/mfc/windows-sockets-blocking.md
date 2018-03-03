---
title: "Сокеты Windows: Блокировка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4b54b78034037e9f3b015d7c1f67bb33771248c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-blocking"></a>Сокеты Windows. Блокировка
В этой статье и в двух статей дополнительное приведены некоторые проблемы в программировании Windows Sockets. В этой статье рассматриваются блокировки. Другие проблемы рассматриваются в статьях: [Windows Sockets: порядок байтов](../mfc/windows-sockets-byte-ordering.md) и [Windows Sockets: преобразование строки](../mfc/windows-sockets-converting-strings.md).  
  
 Если вы используете или являются производными от класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), потребуется самостоятельно управлять эти проблемы. Если вы используете или являются производными от класса [CSocket](../mfc/reference/csocket-class.md), MFC автоматически управляет ими.  
  
## <a name="blocking"></a>Блокировка  
 Сокет может находиться в «режим блокировки» или «неблокирующий режим». Функции сокетов в режиме блокировки (или синхронный) не возвращают до их завершения их действия. Это называется блокировки из-за которого функция была вызвана сокета не может выполнять никаких действий, блокируется, до возвращения вызова. Вызов **Receive** функции-члена, например, может занять произвольно длительное время как оно ожидает отправляющему приложению отправлять (это происходит, если вы используете `CSocket`, или с помощью `CAsyncSocket` с блокировки). Если `CAsyncSocket` объект находится в незаблокированный режим (асинхронно), вызов возвращается немедленно и текущий код ошибки, извлекаемые с [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) функцию-член, **WSAEWOULDBLOCK**, вызов может быть заблокирован, позволяющее определить, был не возвращается немедленно из-за режим. (`CSocket` никогда не возвращает **WSAEWOULDBLOCK**. Этот класс управляет блокировки для вас.)  
  
 Поведение сокетов отличается в 32-разрядных и 64-разрядных операционных систем (например, Windows 95 или Windows 98) чем 16-разрядных операционных систем (например, Windows 3.1). В отличие от 16-разрядных операционных системах 32-разрядных и 64-разрядные операционные системы используйте preemptive многозадачной и укажите многопоточности. В 32-разрядных и 64-разрядных операционных систем, перечисленных в отдельные рабочие потоки можно поместить сокетов. Сокет в поток можно заблокировать не конфликтуют с другими действиями в приложении и не тратить время вычислений на блокировку. Дополнительные сведения о многопоточном программировании см. в статье [многопоточность](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
> [!NOTE]
>  В многопоточных приложениях можно использовать блокировки характер `CSocket` для упрощения разработки программы, не затрагивая скорости реагирования пользовательского интерфейса. С помощью обработки взаимодействия с пользователем в основном потоке и `CSocket` обработки в альтернативные потоки, можно отделить эти логические операции. В приложении, которое не является многопоточным, эти два действия необходимо объединить и обрабатывается как один поток, который обычно достигается использованием `CAsyncSocket` , может обрабатывать запросы связи по запросу или переопределение `CSocket::OnMessagePending` для обработки действий пользователя во время длительных синхронного действия.  
  
 Остальная часть данного обсуждения предназначен для программистов, предназначенных для 16-разрядных операционных системах:  
  
 Как правило при использовании `CAsyncSocket`, следует избегать использования операции блокировки и работает асинхронно вместо. В асинхронных операций получения точки **WSAEWOULDBLOCK** код ошибки после вызова **Receive**, например, можно дождаться вашей `OnReceive` функция-член вызывается для уведомления то, что вы найдете еще раз. Асинхронные вызовы выполняются с помощью вызова обратно сокета соответствующей обратного вызова уведомления функции, такие как [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).  
  
 В группе Windows заблокированных вызовов считается плохой практикой. По умолчанию [CAsyncSocket](../mfc/reference/casyncsocket-class.md) поддерживает асинхронные вызовы и необходимо управлять, блокирующий вручную с помощью обратного вызова уведомления. Класс [CSocket](../mfc/reference/csocket-class.md), с другой стороны, выполняется в синхронном режиме. Он передает сообщения Windows и управляет блокировки для вас.  
  
 Дополнительные сведения о блокировке см. в спецификации Windows Sockets. Дополнительные сведения о функции «On». в разделе [Windows Sockets: уведомления сокетов](../mfc/windows-sockets-socket-notifications.md) и [Windows Sockets: наследование от классов сокета](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)

