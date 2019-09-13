---
title: Сокеты Windows в MFC
ms.date: 11/04/2016
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
ms.openlocfilehash: 44a4838a1cd863bd484701966a156be9f61f8988
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510626"
---
# <a name="windows-sockets-in-mfc"></a>Сокеты Windows в MFC

> [!NOTE]
>  MFC поддерживает сокеты Windows 1, но не поддерживает [сокеты Windows 2](/windows/win32/WinSock/windows-sockets-start-page-2). Windows Sockets 2 впервые поставляется с Windows 98 и является версией, входящей в состав Windows 2000.

MFC предоставляет две модели для написания программ сетевого взаимодействия с помощью сокетов Windows, которые в двух классах MFC. В этой статье описываются эти модели и дополнительные сведения о поддержке сокетов MFC. "Socket" — это конечная точка взаимодействия: объект, с помощью которого приложение взаимодействует с другими приложениями Windows Sockets по сети.

Сведения о сокетах Windows, включая описание концепции сокета, см. в разделе [сокеты Windows: Фон](../mfc/windows-sockets-background.md).

##  <a name="_core_sockets_programming_models"></a>Модели программирования для сокетов

Следующие классы поддерживают две модели программирования сокетов MFC для Windows:

- `CAsyncSocket`

   Этот класс инкапсулирует API-интерфейс сокетов Windows. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) предназначен для программистов, которые узнают о сетевом программировании и хотят обеспечить гибкость программирования непосредственно в API-интерфейсе сокетов, но также хотят, чтобы было удобнее использовать функции обратного вызова для уведомления о сетевых событиях. Кроме упаковки сокетов в объектно-ориентированной форме для использования C++в, единственным дополнительным абстракцией, предоставляемой этим классом, является преобразование определенных сообщений Windows, связанных с сокетом, в обратные вызовы. Дополнительные сведения см. в [разделе сокеты Windows: Уведомления](../mfc/windows-sockets-socket-notifications.md)сокета.

- `CSocket`

   Этот класс, производный `CAsyncSocket`от, предоставляет абстракцию более высокого уровня для работы с сокетами через объект MFC [CArchive](../mfc/reference/carchive-class.md) . Использование сокета с архивом очень напоминает использование протокола сериализации файлов MFC. Это упрощает использование, `CAsyncSocket` чем модель. [CSocket](../mfc/reference/csocket-class.md) наследует многие функции `CAsyncSocket` -члены, которые инкапсулируют API-интерфейсы сокетов Windows. вам придется использовать некоторые из этих функций и разбираться в обычном программировании для сокетов. Но `CSocket` управляет многими аспектами взаимодействия, которые нужно было бы сделать с помощью необработанного API или класса `CAsyncSocket`. Что важнее `CSocket` всего, предоставляет блокировку (с фоновой обработкой сообщений Windows), которая важна для `CArchive`синхронной работы.

Создание и использование `CSocket` объектов `CAsyncSocket` и описывается в [разделе сокеты Windows. Использование сокетов с](../mfc/windows-sockets-using-sockets-with-archives.md) архивами [и сокетами Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>DLL-библиотеки сокетов Windows

Операционные системы Microsoft Windows предоставляют библиотеки динамической компоновки Windows Sockets (DLL). Визуальный C++ элемент предоставляет соответствующие файлы заголовков и библиотеки и спецификацию Windows Sockets.

Дополнительные сведения о сокетах Windows см. в следующих статьях:

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Последовательность операций](../mfc/windows-sockets-sequence-of-operations.md)

- [Сокеты Windows. Пример сокетов с использованием архивов](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Сокеты Windows. Работа сокетов с архивами](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Наследование от классов сокета](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Сокеты Windows. Уведомления сокетов](../mfc/windows-sockets-socket-notifications.md)

- [Сокеты Windows. Блокировка](../mfc/windows-sockets-blocking.md)

- [Сокеты Windows. Порядок байтов](../mfc/windows-sockets-byte-ordering.md)

- [Сокеты Windows. Преобразование строк](../mfc/windows-sockets-converting-strings.md)

- [Сокеты Windows. Порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>См. также

[Сокеты Windows](../mfc/windows-sockets.md)
