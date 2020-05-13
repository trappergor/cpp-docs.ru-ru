---
title: Сокеты Windows. Использование класса CAsyncSocket
ms.date: 11/04/2016
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: d3fc32d9da54d9cf8c79e9e5de45b81c2ef64a6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371972"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Сокеты Windows. Использование класса CAsyncSocket

В этой статье объясняется, как использовать класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Имейте в виду, что этот класс инкапсулирует API Sockets Windows на очень низком уровне. `CAsyncSocket`используется программистами, которые знают сетевые коммуникации в деталях, но хотят удобство обратных вызовов для уведомления о сетевых событиях. Основываясь на этом предположении, эта статья содержит только основные инструкции. Вы, вероятно, `CAsyncSocket` следует рассмотреть возможность использования, если вы хотите Windows Sockets 'легкость работы с несколькими сетевыми протоколами в приложении MFC, но не хотите жертвовать гибкостью. Вы также можете почувствовать, что вы можете получить более высокую эффективность, программируя `CSocket`сообщения более непосредственно себя, чем вы могли бы с помощью более общей альтернативной модели класса.

`CAsyncSocket`задокументировано в *справочнике МФЦ.* Visual C ' также поставляет спецификацию Windows Sockets, расположенную в SDK Windows. Детали остаются за вами. Визуальный СЗ не поставляет образец приложения для `CAsyncSocket`.

Если вы не очень хорошо осведомлены о сетевой коммуникации и `CArchive` хотите простое решение, используйте класс [CSocket](../mfc/reference/csocket-class.md) с объектом. Для получения дополнительной информации можно увидеть [розетки windows: Использование розеток с архивами.](../mfc/windows-sockets-using-sockets-with-archives.md)

В этой статье рассматриваются следующие вопросы:

- Создание и `CAsyncSocket` использование объекта.

- [Ваши обязанности с CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).

## <a name="creating-and-using-a-casyncsocket-object"></a><a name="_core_creating_and_using_a_casyncsocket_object"></a>Создание и использование объекта CAsyncSocket

#### <a name="to-use-casyncsocket"></a>Для использования CAsyncSocket

1. Постройте объект [CAsyncSocket](../mfc/reference/casyncsocket-class.md) и используйте объект для создания основной ручки **SOCKET.**

   Создание розетки следует шаблону MFC двухступенчатой конструкции.

   Пример:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     -или-

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Первый конструктор выше `CAsyncSocket` создает объект на стеке. Второй конструктор создает `CAsyncSocket` на куче. Первый [вызов Create](../mfc/reference/casyncsocket-class.md#create) выше использует параметры по умолчанию для создания разъема потока. Второй `Create` вызов создает разъем для данных с указанным портом и адресом. (Вы можете `Create` использовать любой вариант с любым методом конструкции.)

   Параметры: `Create`

   - "Порт": короткий ряд.

      Для разъема сервера необходимо указать порт. Для разъема клиента обычно принимается значение по умолчанию для этого параметра, которое позволяет Windows Sockets выбрать порт.

   - Тип розетки: **SOCK_STREAM** (по умолчанию) или **SOCK_DGRAM.**

   - Разъем "адрес", например "ftp.microsoft.com" или "128.56.22.8".

      Это ваш адрес Интернет-протокола (IP) в сети. Вы, вероятно, всегда будете полагаться на значение по умолчанию для этого параметра.

   Термины "порт" и "адрес розетки" разъясняются в [Windows Sockets: Порты и адреса розетки.](../mfc/windows-sockets-ports-and-socket-addresses.md)

1. Если розетка является клиентом, подключите объект розетки к разъему сервера, используя [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect).

     -или-

   Если розетка является сервером, установите розетку, чтобы начать прослушивание (с [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) для попыток подключения от клиента. После получения запроса на подключение, примите его с [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).

   После принятия соединения можно выполнить такие задачи, как проверка паролей.

    > [!NOTE]
    >  Функция `Accept` члена берет в качестве параметра ссылку на новый пустой `CSocket` объект. Вы должны построить этот `Accept`объект, прежде чем вы звоните. Если этот объект розетки выходит за рамки, соединение закрывается. Не вызывайте `Create` этот новый объект розетки. Например, см. [Windows Sockets: Sequence of Operations](../mfc/windows-sockets-sequence-of-operations.md)

1. Выполняй связь с другими розетками, вызывая функции члена `CAsyncSocket` объекта, которые инкапсулируют функции API Windows Sockets.

   Смотрите спецификацию Windows Sockets и класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md) в *справочнике MFC.*

1. Уничтожить `CAsyncSocket` объект.

   Если объект розетки в стеке создается, его деструктор вызывается, когда содержащая функция выходит за рамки. Если вы создали объект розетки на куче, используя **нового** оператора, вы несете ответственность за использование оператора **удаления** для уничтожения объекта.

   Деструктор вызывает функцию [члена близкого](../mfc/reference/casyncsocket-class.md#close) объекта перед уничтожением объекта.

Пример этой последовательности в коде `CSocket` (на самом деле для объекта) см. Windows [Sockets: Sequence of Operations.](../mfc/windows-sockets-sequence-of-operations.md)

## <a name="your-responsibilities-with-casyncsocket"></a><a name="_core_your_responsibilities_with_casyncsocket"></a>Ваши обязанности с CAsyncSocket

При создании объекта класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md)объект инкапсулирует ручку **Windows SOCKET** и поставляет операции на этой ручке. При использовании `CAsyncSocket`необходимо решать все проблемы, с которыми вы можете столкнуться при непосредственном использовании API. Пример:

- "Блокировка" сценариев.

- Byte заказ различия между отправкой и приемной машин.

- Преобразование между строками Unicode и набором мультибайт (MBCS).

Для определения этих терминов и дополнительной информации, см [Windows розетки: Блокировка](../mfc/windows-sockets-blocking.md), [Windows розетки: Байт Заказ](../mfc/windows-sockets-byte-ordering.md), Windows [розетки: Преобразование строк](../mfc/windows-sockets-converting-strings.md).

Несмотря на `CAsycnSocket` эти проблемы, класс может быть правильным выбором для вас, если ваше приложение требует всей гибкости и контроля, которые вы можете получить. Если нет, то следует `CSocket` рассмотреть возможность использования класса вместо этого. `CSocket`скрывает много деталей от вас: он насосы Windows сообщений `CArchive`во время блокирования звонков и дает вам доступ к , который управляет байт разница в порядке и строки преобразования для вас.

Дополнительные сведения см. в разделе:

- [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также раздел

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
