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
ms.openlocfilehash: 8e5562b028d3d9b7cba4b47716b63fd1392c514f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371098"
---
# <a name="windows-sockets-in-mfc"></a>Сокеты Windows в MFC

> [!NOTE]
> MFC поддерживает Windows Sockets 1, но не поддерживает [Windows Sockets 2](/windows/win32/WinSock/windows-sockets-start-page-2). Windows Sockets 2 впервые поставляется с Windows 98 и является версия, включенная с Windows 2000.

MFC поставляет две модели для написания сетевых программ связи с Windows Sockets, воплощенные в двух классах MFC. В этой статье описаны эти модели и более подробная информация MFC розетки поддержки. "Разъем" является конечной точкой связи: объект, через который приложение общается с другими приложениями Windows Sockets по всей сети.

Для получения информации о Windows Розетки, в том числе объяснение концепции розетки, [см.](../mfc/windows-sockets-background.md)

## <a name="sockets-programming-models"></a><a name="_core_sockets_programming_models"></a>Модели программирования розеток

Две модели программирования MFC Windows Sockets поддерживаются следующими классами:

- `CAsyncSocket`

   Этот класс инкапсулирует API sockets Windows. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) предназначен для программистов, которые знают сетевое программирование и хотят гибкость программирования непосредственно на aPI розеток, но также хотят удобство функций обратного вызова для уведомления о сетевых событиях. Помимо упаковки розеток в объектно-ориентированной форме для использования в СЗ, единственной дополнительной абстракцией, которая предоставляет сярвые материалы этого класса, является преобразование определенных сообщений Windows, связанных с розетками, в обратные вызовы. Для получения дополнительной [информации см.](../mfc/windows-sockets-socket-notifications.md)

- `CSocket`

   Этот класс, полученный из, `CAsyncSocket`поставляет более высокий уровень абстракции для работы с розетками через объект MFC [CArchive.](../mfc/reference/carchive-class.md) Использование розетки с архивом очень напоминает с помощью протокола сериализации файлов MFC. Это упрощает использование `CAsyncSocket` модели. [CSocket](../mfc/reference/csocket-class.md) наследует многие `CAsyncSocket` функции членов из этого инкапсулировать Windows Sockets AIS; вам придется использовать некоторые из этих функций и понять разъемы программирования в целом. Но `CSocket` управляет многими аспектами коммуникации, что вам придется сделать `CAsyncSocket`самостоятельно, используя либо сырой API или класса. Самое главное, `CSocket` обеспечивает блокировку (с фоновой обработкой сообщений `CArchive`Windows), которая имеет важное значение для синхронной работы .

Создание и `CSocket` `CAsyncSocket` использование объектов описано в [Windows Sockets: Использование розеток с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) и [Windows Sockets: Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).

## <a name="windows-sockets-dlls"></a><a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>Окна разъемы DLLs

Операционные системы Microsoft Windows поставляют библиотеки динамической связи Windows Sockets (DLL). Visual C' поставляет соответствующие файлы заголовка и библиотеки и спецификацию Windows Sockets.

Для получения дополнительной информации о Windows Sockets см.:

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

## <a name="see-also"></a>См. также раздел

[Сокеты Windows](../mfc/windows-sockets.md)
