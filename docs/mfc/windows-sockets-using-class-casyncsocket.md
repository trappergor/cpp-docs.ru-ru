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
ms.openlocfilehash: 6a3b3469b908eaf6f8062b8db7fc4287606b7f02
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228509"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Сокеты Windows. Использование класса CAsyncSocket

В этой статье объясняется, как использовать класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Имейте в виду, что этот класс инкапсулирует API Windows Sockets на очень низком уровне. `CAsyncSocket`предназначен для использования программистами, которые узнают о сетевом взаимодействии, но хотят использовать обратные вызовы для уведомления о сетевых событиях. Основываясь на этом предположении, в этой статье содержится только основная инструкция. Вы, вероятно, рассмотрите возможность использования, `CAsyncSocket` Если вы хотите, чтобы использование сокетов Windows было удобным для работы с несколькими сетевыми протоколами в приложении MFC, но не хотите пожертвовать гибкостью. Кроме того, вы можете получить лучшую эффективность благодаря более эффективному программированию взаимодействия, чем использовать более общую альтернативную модель класса `CSocket` .

`CAsyncSocket`описывается в *справочнике по MFC*. Visual C++ также предоставляет спецификацию сокетов Windows, расположенную в Windows SDK. Сведения отправляются по левому краю. Visual C++ не предоставляет пример приложения для `CAsyncSocket` .

Если вы не обладаете широкими знаниями о сетевых подключениях и хотите использовать простое решение, используйте класс [CSocket](../mfc/reference/csocket-class.md) с `CArchive` объектом. Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) .

В этой статье рассматриваются следующие вопросы:

- Создание и использование `CAsyncSocket` объекта.

- [Ваши обязанности с CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).

## <a name="creating-and-using-a-casyncsocket-object"></a><a name="_core_creating_and_using_a_casyncsocket_object"></a>Создание и использование объекта CAsyncSocket

#### <a name="to-use-casyncsocket"></a>Использование CAsyncSocket

1. Создайте объект [CAsyncSocket](../mfc/reference/casyncsocket-class.md) и используйте объект для создания базового маркера **сокета** .

   Создание сокета соответствует шаблону MFC для создания двух этапов.

   Пример:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     -или-

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Первый приведенный выше конструктор создает `CAsyncSocket` объект в стеке. Второй конструктор создает объект `CAsyncSocket` в куче. Первый вызов [CREATE](../mfc/reference/casyncsocket-class.md#create) выше использует параметры по умолчанию для создания сокета потока. Второй `Create` вызов создает сокет датаграммы с указанным портом и адресом. (Можно использовать любую из `Create` версий с любым методом создания.)

   Параметры `Create` :

   - "Port": короткое целое число.

      Для сокета сервера необходимо указать порт. Для сокета клиента обычно принимается значение по умолчанию для этого параметра, что позволяет использовать сокеты Windows для выбора порта.

   - Тип сокета: **SOCK_STREAM** (по умолчанию) или **SOCK_DGRAM**.

   - Адрес сокета, например "ftp.microsoft.com" или "128.56.22.8".

      Это IP-адрес в сети. Вы, вероятно, всегда полагаетесь на значение по умолчанию для этого параметра.

   Термины "порт" и "адрес сокета" описаны в [подокнах сокетов Windows: порты и адреса сокетов](../mfc/windows-sockets-ports-and-socket-addresses.md).

1. Если сокет является клиентом, подключите объект сокета к сокету сервера с помощью [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect).

     -или-

   Если сокет является сервером, задайте для сокета начало прослушивания (с помощью [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen)) для попыток подключения клиента. После получения запроса на подключение примите его с помощью [CAsyncSocket:: Accept](../mfc/reference/casyncsocket-class.md#accept).

   После принятия подключения можно выполнять такие задачи, как проверка паролей.

    > [!NOTE]
    >  `Accept`Функция-член принимает ссылку на новый пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода `Accept` . Если этот объект сокета выходит за пределы области действия, соединение закрывается. Не вызывайте `Create` этот новый объект сокета. Пример см. в статье [сокеты Windows: последовательность операций](../mfc/windows-sockets-sequence-of-operations.md).

1. Выполните обмен данными с другими сокетами, вызвав `CAsyncSocket` функции-члены объекта, которые инкапсулируют функции API сокетов Windows.

   См. спецификацию сокетов Windows и класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md) в *справочнике по MFC*.

1. Удалите `CAsyncSocket` объект.

   Если объект сокета был создан в стеке, его деструктор вызывается, когда содержащая ее функция выходит за пределы области. Если вы создали объект сокета в куче с помощью **`new`** оператора, вы несете ответственность за использование **`delete`** оператора для уничтожения объекта.

   Перед уничтожением объекта деструктор вызывает функцию [закрытия](../mfc/reference/casyncsocket-class.md#close) элемента объекта.

Пример этой последовательности в коде (на самом деле для `CSocket` объекта) см. в разделе [сокеты Windows: последовательность операций](../mfc/windows-sockets-sequence-of-operations.md).

## <a name="your-responsibilities-with-casyncsocket"></a><a name="_core_your_responsibilities_with_casyncsocket"></a>Ваши обязанности с CAsyncSocket

При создании объекта класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md)объект инкапсулирует маркер Windows **Socket** и предоставляет операции с этим маркером. При использовании вы `CAsyncSocket` должны иметь дело со всеми проблемами, которые могут возникнуть при непосредственном использовании API. Например:

- Сценарии блокировки.

- Различия порядка байтов между отправляющей и принимающей машинами.

- Преобразование между строками Юникода и многобайтовой кодировкой (MBCS).

Определения этих терминов и дополнительные сведения см. в статьях [сокеты Windows: Блокировка](../mfc/windows-sockets-blocking.md), [сокеты Windows: порядок байтов](../mfc/windows-sockets-byte-ordering.md), [сокеты Windows: преобразование строк](../mfc/windows-sockets-converting-strings.md).

Несмотря на эти проблемы, класс `CAsycnSocket` может быть правильным выбором, если ваше приложение требует всей гибкости и управления, которые можно получить. Если нет, вместо этого следует использовать класс `CSocket` . `CSocket`скрывает от вас много деталей: он переносит сообщения Windows во время блокирующих вызовов и предоставляет вам доступ к `CArchive` , который управляет различиями порядка байтов и преобразованием строк.

Дополнительные сведения см. в разделе:

- [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

- [Сокеты Windows: сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows: сокеты датаграммы](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также статью

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
