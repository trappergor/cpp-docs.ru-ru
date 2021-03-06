---
title: Сокеты Windows. Блокировка
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 87d4f0eb57f9e26dbf73da06b5d7ca6d61d6c174
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360000"
---
# <a name="windows-sockets-blocking"></a>Сокеты Windows. Блокировка

В этой статье и двух сопутствующих статьях объясняется несколько проблем в программировании Windows Sockets. Эта статья охватывает блокировку. Другие вопросы описаны в статьях: [Windows Sockets: Заказ байта](../mfc/windows-sockets-byte-ordering.md) и [розетки Windows: Преобразование струнных.](../mfc/windows-sockets-converting-strings.md)

Если вы используете или вытекают из класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), вам нужно будет управлять этими вопросами самостоятельно. Если вы используете или вытекают из класса [CSocket,](../mfc/reference/csocket-class.md)MFC управляет ими для вас.

## <a name="blocking"></a>Блокировка

Разъем может находиться в "режиме блокировки" или "режиме неблокировки". Функции розеток в блокирующем (или синхронном) режиме не возвращаются, пока они не смогут завершить свое действие. Это называется блокировкой, потому что розетка, функция которой была вызвана, ничего не может сделать - блокируется - до тех пор, пока вызов не вернется. Например, `Receive` для завершения вызова к функции участника может потребоваться произвольно длительное время, так как он ждет `CSocket`отправки `CAsyncSocket` приложения для отправки (это если вы используете или используете с блокировкой). Если `CAsyncSocket` объект находится в режиме неблокировки (работает асинхронно), вызов возвращается немедленно и текущий код ошибки, извлекаемый с функцией [getLastError,](../mfc/reference/casyncsocket-class.md#getlasterror) является **WSAEWOULDBLOCK**, указывая, что вызов был бы заблокирован, если бы он не вернулся немедленно из-за режима. (`CSocket` никогда не возвращает **WSAEWOULDBLOCK**. Класс управляет блокировкой для вас.)

Поведение розеток отличается под 32-разрядными и 64-разрядными операционными системами (такими как Windows 95 или Windows 98), чем под 16-разрядными операционными системами (например, Windows 3.1). В отличие от 16-разрядных операционных систем, 32-разрядные и 64-разрядные операционные системы используют упреждающую многозадачность и обеспечивают многопоточность. Под 32-разрядные и 64-разрядные операционные системы можно поместить розетки в отдельные рабочие нити. Розетка в потоке может блокироваться, не мешая другим действиям в приложении и не тратя время на блокировку. Для получения информации о многопоточном программировании см. [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md)

> [!NOTE]
> В многопоточных приложениях можно использовать `CSocket` блокирующий характер для упрощения дизайна программы, не влияя на отзывчивость пользовательского интерфейса. Обработка взаимодействия пользователей в `CSocket` основном потоке и обработка в альтернативных потоках можно разделить эти логические операции. В приложении, которое не является многопоточной, эти два действия должны быть `CAsyncSocket` объединены и обработаны как единый поток, что обычно означает использование, чтобы вы могли обрабатывать запросы на связь по требованию, или переопределение `CSocket::OnMessagePending` для обработки действий пользователя во время длительной синхронной деятельности.

Остальная часть обсуждения для программистов, ориентированных на 16-разрядные операционные системы:

Обычно, если вы `CAsyncSocket`используете, вы должны избегать использования блокирующих операций и работать асинхронно вместо. В асинхронных операциях, с момента получения кода ошибки **WSAEWOULDBLOCK** после звонка, `Receive`например, вы ждете, пока ваша `OnReceive` функция члена будет вызвана, чтобы уведомить вас, что вы можете прочитать снова. Асинхронные звонки совершаться путем перезвона соответствующей функции уведомления обратного вызова вашего гнезда, такой как [OnReceive.](../mfc/reference/casyncsocket-class.md#onreceive)

Под Windows блокировка вызовов считается плохой практикой. По умолчанию [CAsyncSocket](../mfc/reference/casyncsocket-class.md) поддерживает асинхронные вызовы, и вы должны управлять блокировкой самостоятельно, используя уведомления обратного вызова. Класс [CSocket](../mfc/reference/csocket-class.md), с другой стороны, синхронный. Он перекачивает сообщения Windows и управляет блокировкой для вас.

Для получения дополнительной информации о блокировке см. Для получения дополнительной информации о функциях "На" см. [Windows Розетки: Уведомления розетки](../mfc/windows-sockets-socket-notifications.md) и [Windows Розетки: Получение из разъема классов](../mfc/windows-sockets-deriving-from-socket-classes.md).

Дополнительные сведения см. в разделе:

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)

- [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)

- [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>См. также раздел

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)
