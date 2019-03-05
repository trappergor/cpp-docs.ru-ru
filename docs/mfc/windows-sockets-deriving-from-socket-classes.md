---
title: Сокеты Windows. Наследование от классов сокета
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
ms.openlocfilehash: 12ab66cfd9212cd79752e2f6359b857194c6428c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270332"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Сокеты Windows. Наследование от классов сокета

В этой статье описываются некоторые функциональные возможности, которые можно получить путем наследования от одного из классов сокетов свой собственный класс.

Можно унаследовать собственных классов сокета либо [CAsyncSocket](../mfc/reference/casyncsocket-class.md) или [CSocket](../mfc/reference/csocket-class.md) для добавления собственных функций. В частности эти классы указать ряд виртуальных функций-членов, которые можно переопределить. К этим функциям относятся [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), и [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Функции можно переопределить в классе производном сокета позволяет воспользоваться преимуществами уведомлений, которые они предоставляют при возникновении события сети. Платформа вызывает эти функции обратного вызова уведомления об изменениях сокета важных событий, таких как прием данных, можно начать чтение. Дополнительные сведения о функции уведомления, см. в разделе [сокеты Windows: Сокета уведомления](../mfc/windows-sockets-socket-notifications.md).

Кроме того, класс `CSocket` предоставляет [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) функция-член (это усовершенствованное переопределяемый). MFC вызывает эту функцию, пока сокет является цикл обработки сообщений на основе Windows. Можно переопределить `OnMessagePending` для поиска определенного сообщения из Windows и реагирования на них.

Стандартная версия `OnMessagePending` указан в классе `CSocket` проверяет очередь для сообщений WM_PAINT при ожидании блокирующий вызов для завершения. Он отправляет сообщения рисования для повышения качества изображения. Помимо сделать что-нибудь полезное, это иллюстрирует один из способов, переопределите функцию самостоятельно. Например, рассмотрите возможность использования `OnMessagePending` для следующей задачи. Предположим, что отображение немодального диалогового окна при ожидании завершения транзакции сети. Диалоговое окно содержит кнопки "Отмена", который пользователь может использовать для отмены блокирующие транзакции, которые слишком долго. Ваш `OnMessagePending` переопределения может передавать сообщения, связанные с этой немодальное диалоговое окно.

В вашей `OnMessagePending` переопределения, возвращать **TRUE** или возврат из вызова версии базового класса `OnMessagePending`. Вызовите версию базового класса, если он выполняет работу, которую вы все равно хотите сделать.

Дополнительные сведения:

- [Сокеты Windows. Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Сокеты Windows. Использование класса CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Сокеты Windows. Блокировки](../mfc/windows-sockets-blocking.md)

- [Сокеты Windows. Порядок байтов](../mfc/windows-sockets-byte-ordering.md)

- [Сокеты Windows. Преобразование строк](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)
