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
ms.openlocfilehash: 9992d2054c04eea1b3b63d591601acf0091acb5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348566"
---
# <a name="windows-sockets-in-mfc"></a>Сокеты Windows в MFC

> [!NOTE]
>  MFC поддерживает 1 сокетов Windows, но не поддерживает [Windows Sockets 2](/windows/desktop/WinSock/windows-sockets-start-page-2). Windows Sockets 2 сначала с Windows 98 и версия включена в Windows 2000.

MFC предоставляет две модели для написания программы связи сети с помощью сокетов Windows, воплощенные в двух классах MFC. В этой статье описаны эти модели и их подробнее MFC сокеты поддержки. «Сокета» — это конечная точка связи: объект с помощью которого приложение взаимодействует с другими приложениями сокетов Windows по сети.

Сведения о Windows Sockets, включая пояснения концепции сокета, см. в разделе [сокеты Windows: фон](../mfc/windows-sockets-background.md).

##  <a name="_core_sockets_programming_models"></a> Сокеты, модели программирования

Два разъема MFC Windows, модели программирования поддерживаются следующие классы:

- `CAsyncSocket`

   Этот класс инкапсулирует Windows Sockets API. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) для программистов, которые знать Сетевое программирование и нуждается в гибкой программирования непосредственно для API сокетов, но также требуется удобство функций обратного вызова для уведомления о событиях в сети. Кроме упаковка сокетов в объектно ориентированного форме для использования в C++, только дополнительные абстракции, который предоставляет этот класс преобразует определенных сообщений, связанных с сокетов Windows в обратных вызовов. Дополнительные сведения см. в разделе [сокеты Windows: Сокета уведомления](../mfc/windows-sockets-socket-notifications.md).

- `CSocket`

   Этот класс производным от `CAsyncSocket`, предоставляет выше уровня абстракции для работы с сокетов MFC [CArchive](../mfc/reference/carchive-class.md) объекта. Использование сокета с архивом значительно напоминает применение сериализации протокол MFC. Это упрощает в использовании, чем `CAsyncSocket` модели. [CSocket](../mfc/reference/csocket-class.md) наследует многие функции-члены из `CAsyncSocket` который инкапсулировать API сокетов Windows, необходимо будет использовать некоторые из этих функций и понимание обычно программировании сокетов. Но `CSocket` управляет многими аспектами обмен данными, пришлось бы сделать самостоятельно с помощью необработанных API или класс `CAsyncSocket`. Самое главное `CSocket` предоставляет блокировки (с фоновой обработкой сообщений Windows), что является необходимым для синхронной операции из `CArchive`.

Создание и использование `CSocket` и `CAsyncSocket` объекты описан в [сокеты Windows: Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) и [сокеты Windows: Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets библиотек DLL

В операционных системах Microsoft Windows укажите Windows Sockets библиотеки динамической компоновки (DLL). Visual C++ предоставляет необходимые файлы заголовка и библиотеки в спецификации Windows Sockets.

Дополнительные сведения о Windows Sockets см. в разделе:

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
