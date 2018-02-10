---
title: "Сокеты Windows в MFC | Документы Microsoft"
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
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 187a58e719ad320975deba7429d6ec04a70143ac
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="windows-sockets-in-mfc"></a>Сокеты Windows в MFC
> [!NOTE]
>  MFC поддерживает Windows Sockets 1, но не поддерживает [Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673). Сначала Windows Sockets 2, поставляемых с Windows 98 и имеет версию, включенную в Windows 2000.  
  
 MFC предоставляет две модели для написания программ связи сети с помощью сокетов Windows, встроенного в двух классов MFC. В этой статье описываются эти модели и Дополнительные сведения о MFC сокеты поддержки. «Сокет» — это конечная точка связи: объект с помощью которого приложение взаимодействует с другими приложениями сокетов Windows по сети.  
  
 Сведения о Windows Sockets, включая пояснения концепции сокета, содержатся [Windows Sockets: фон](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a>Сокеты, модели программирования  
 Две модели программирования MFC Windows Sockets поддерживаются следующие классы:  
  
-   `CAsyncSocket`  
  
     Этот класс инкапсулирует Windows Sockets API. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) предназначена для программистов, знать Сетевое программирование и гибкости программирования непосредственно к сокетам API а также должны удобных функций обратного вызова для уведомления о событиях в сети. Кроме упаковка сокетов в объектно ориентированном формате для использования в C++, только дополнительные абстракции, которые предоставляет этот класс является преобразование определенных сокетов Windows сообщений о обратных вызовов. Дополнительные сведения см. в разделе [Windows Sockets: уведомления сокетов](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Этот класс, производный от `CAsyncSocket`, предоставляющий высокий уровень абстракции для работы с помощью сокетов через MFC [CArchive](../mfc/reference/carchive-class.md) объекта. Использование сокета с архив значительно напоминает протоколу MFC файл сериализации. Это упрощает по сравнению с `CAsyncSocket` модели. [CSocket](../mfc/reference/csocket-class.md) наследует многие функции-члены из `CAsyncSocket` , инкапсулируют API-интерфейсы Windows Sockets; необходимо будет использовать некоторые из этих функций и понять, обычно программировании сокетов. Но `CSocket` управляет многие аспекты связи, который необходимо сделать самостоятельно с помощью необработанных API-Интерфейс или класс `CAsyncSocket`. Самое главное `CSocket` предоставляет блокировки (с фоновой обработки сообщений Windows), что является необходимым для синхронной операции из `CArchive`.  
  
 Создание и использование `CSocket` и `CAsyncSocket` объекты описан в [Windows Sockets: с помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) и [Windows Sockets: использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>DLL-библиотеки сокетов Windows  
 Операционные системы Microsoft Windows укажите Windows Sockets библиотеки динамической компоновки (DLL). Visual C++ предоставляет необходимые файлы заголовка и библиотеки спецификации Windows Sockets.  
  
 Дополнительные сведения о Windows Sockets см.:  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Сокеты Windows. Последовательность операций](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Сокеты Windows. Пример сокетов с использованием архивов](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Сокеты Windows. Работа сокетов с архивами](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Сокеты Windows. Наследование от классов сокета](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Сокеты Windows. Уведомления сокетов](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Сокеты Windows. Блокировка](../mfc/windows-sockets-blocking.md)  
  
-   [Сокеты Windows. Порядок байтов](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Сокеты Windows. Преобразование строк](../mfc/windows-sockets-converting-strings.md)  
  
-   [Сокеты Windows. Порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows](../mfc/windows-sockets.md)

