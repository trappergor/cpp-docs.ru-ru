---
title: Сокеты Windows. Использование класса CAsyncSocket
ms.date: 11/04/2016
f1_keywords:
- CAsyncSocket
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: 51274791393d95517bd8de5ae7248dc634018037
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263117"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Сокеты Windows. Использование класса CAsyncSocket

В этой статье объясняется, как использовать класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Имейте в виду, что этот класс инкапсулирует API сокетов Windows, на очень низком уровне. `CAsyncSocket` предназначен для использования программистами, знать сетевых подключений, подробно, но хотите удобство обратные вызовы для уведомления о событиях в сети. В этой статье, с учетом это предположение, предоставляет только основные инструкция. Возможно, следует рассмотреть возможность использования `CAsyncSocket` Если действия для упрощения работы с нескольких сетевых протоколов в приложениях MFC Windows Sockets, но не хотите пожертвовать гибкостью. Вам также может быть, повышения эффективности можно получить от программирования дополнительные связи, напрямую самостоятельно, чем у вас может с помощью модели более общими класса `CSocket`.

`CAsyncSocket` описан в *Справочник по библиотеке MFC*. Visual C++ также предоставляет спецификации Windows Sockets, расположенный в пакете SDK для Windows. Сведения о которых возлагается на вас. Visual C++ не предоставляет образец приложения для `CAsyncSocket`.

Если вы не очень разбираются в сети и простое решение, используйте класс [CSocket](../mfc/reference/csocket-class.md) с `CArchive` объекта. См. в разделе [сокеты Windows: Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) Дополнительные сведения.

В этой статье рассматриваются следующие действия:

- Создание и использование `CAsyncSocket` объекта.

- [Ваши обязанности с CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).

##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Создание и использование объекта CAsyncSocket

#### <a name="to-use-casyncsocket"></a>Чтобы использовать CAsyncSocket

1. Создать [CAsyncSocket](../mfc/reference/casyncsocket-class.md) объекта и использовать объект для создания базового **СОКЕТА** обработки.

   Создание сокета по шаблону MFC конструкции два этапа.

   Пример:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     - или -

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Первый конструктор выше создает `CAsyncSocket` объект в стеке. Второй конструктор создает `CAsyncSocket` в куче. Первый [создать](../mfc/reference/casyncsocket-class.md#create) выше вызов использует параметры по умолчанию для создания потока сокета. Второй `Create` вызов создает сокета датаграмм с указанного порта и адрес. (Можно использовать любой `Create` версии независимо от выбранного способа построения.)

   Параметры, которые `Create` являются:

   - «Порт»: короткое целое число.

         For a server socket, you must specify a port. For a client socket, you typically accept the default value for this parameter, which lets Windows Sockets select a port.

   - Тип сокета: **SOCK_STREAM** (по умолчанию) или **SOCK_DGRAM**.

   - Соединение «address», например «ftp.microsoft.com» или «128.56.22.8».

         This is your Internet Protocol (IP) address on the network. You will probably always rely on the default value for this parameter.

   Термины «порт» и «адрес сокета» описаны в [сокеты Windows: Порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md).

1. Если сокет является клиентом, подключить объект сокета к серверу сокетов, с помощью [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect).

     - или -

   Если сокет сервера, задайте сокета, чтобы начать прослушивать вызовы (с [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) для попыток подключиться из клиента. При получении запроса на подключение, примите его с [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).

   После принятия запроса на подключения, можно выполнить такие задачи, как проверки паролей.

    > [!NOTE]
    >  `Accept` Функция-член принимает ссылку на новую, пустую `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода `Accept`. Если этот объект сокета выходит за пределы области, закрывает соединение. Не вызывайте `Create` для этого нового объекта сокета. Например, см. в статье [сокеты Windows: Последовательность операций](../mfc/windows-sockets-sequence-of-operations.md).

1. Выполнять обмен данными с другими сокетов, вызывая `CAsyncSocket` функций-членов объекта, которые инкапсулируют функций API сокетов Windows.

   См. в спецификации Windows Sockets и класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md) в *Справочник по библиотеке MFC*.

1. Уничтожить `CAsyncSocket` объекта.

   Если вы создали объект сокета в стеке, его деструктор вызывается в том случае, когда содержащего функция выходит за пределы области. Если вы создали объект сокета в куче, с помощью **новый** оператор, вы несете ответственность за использование **удалить** оператор уничтожаемый объект.

   Деструктор вызывает объекта [закрыть](../mfc/reference/casyncsocket-class.md#close) функция-член перед удалением объекта.

Пример этой последовательности в коде (фактически для `CSocket` объекта), см. в разделе [сокеты Windows: Последовательность операций](../mfc/windows-sockets-sequence-of-operations.md).

##  <a name="_core_your_responsibilities_with_casyncsocket"></a> Ваши обязанности с CAsyncSocket

При создании объекта класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), которую инкапсулирует объект Windows **СОКЕТА** обработки и предоставляет операции для этого дескриптора. При использовании `CAsyncSocket`, которые нужно решить все проблемы, которые могут возникнуть при использовании API напрямую. Пример:

- Сценарии «Блокировка».

- Различия порядок байтов между отправляющим и принимающим машин.

- Преобразование между Юникодом и многобайтовой набора строк (MBCS).

Определения этих терминов и Дополнительные сведения см. в разделе [сокеты Windows: Блокировка](../mfc/windows-sockets-blocking.md), [сокеты Windows: Порядок байтов](../mfc/windows-sockets-byte-ordering.md), [сокеты Windows: Преобразование строк](../mfc/windows-sockets-converting-strings.md).

Несмотря на эти проблемы класса `CAsycnSocket` может быть правильным выбором для вас, если приложению требуется гибкость и управления, можно получить. Если нет, можно использовать класс `CSocket` вместо этого. `CSocket` скрывает много подробных сведений от вас: направляет сообщения во время блокирующих вызовов Windows, а также предоставляет доступ к ИТ `CArchive`, который управляет различия порядок байтов и преобразования строк для вас.

Дополнительные сведения:

- [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

- [Сокеты Windows. Сокеты Stream](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
