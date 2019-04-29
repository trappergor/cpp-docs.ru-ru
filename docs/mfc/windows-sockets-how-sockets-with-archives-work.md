---
title: Сокеты Windows. Работа сокетов с архивами
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 3af94bc881276238f1a8d2dbeeee4dca1f173a4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389453"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Сокеты Windows. Работа сокетов с архивами

В этой статье объясняется, как [CSocket](../mfc/reference/csocket-class.md) объекта, [CSocketFile](../mfc/reference/csocketfile-class.md) объекта и [CArchive](../mfc/reference/carchive-class.md) объект объединяются для упрощают отправку и получение данных с помощью Windows Сокет.

Статья [сокеты Windows: Пример сокетов с использованием архивов](../mfc/windows-sockets-example-of-sockets-using-archives.md) представляется `PacketSerialize` функции. Объект архива в `PacketSerialize` пример будет работать аналогично архив объектом, переданным MFC [Serialize](../mfc/reference/cobject-class.md#serialize) функции. Essential разница заключается в том, что для сокетов, архив прикреплена не со стандартом [CFile](../mfc/reference/cfile-class.md) (обычно связан с файлом на диске) объекта а `CSocketFile` объекта. Вместо того чтобы подключаться в файл на диске, `CSocketFile` объект подключается к `CSocket` объекта.

Объект `CArchive` объекта управляет буфером. При заполнении буфера хранения архива (отправка), связанным `CFile` объект записывает содержимое буфера. Запись на диск буфера архив, подключенное к разъему эквивалентно отправке сообщения. При переполнении буфера архива загрузка (получение), `CFile` объект останавливает чтение, пока буфер снова станет доступным.

Класс `CSocketFile` является производным от `CFile`, но он не поддерживает [CFile](../mfc/reference/cfile-class.md) член функции, такие как функции размещения (`Seek`, `GetLength`, `SetLength`, и т. д), блокировка функций ( `LockRange`, `UnlockRange`), или `GetPosition` функции. Все [CSocketFile](../mfc/reference/csocketfile-class.md) объекта необходимо выполнить запись или чтение последовательности байтов, или из связанного `CSocket` объекта. Поскольку файл не участвует, операции, такие как `Seek` и `GetPosition` не имеет смысла. `CSocketFile` является производным от `CFile`, поэтому он обычно будет наследовать все эти функции-члены. Чтобы избежать этого, неподдерживаемое `CFile` функции-члены переопределены в `CSocketFile` исключение [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).

`CSocketFile` Объект вызывает член функции его `CSocket` объект для отправки и получения данных.

На следующем рисунке показана отношения между этими объектами на обеих сторонах связи.

![CArchive, CSocketFile и CSocket](../mfc/media/vc38ia1.gif "CArchive, CSocketFile и CSocket") <br/>
CArchive, CSocketFile и CSocket

Это излишне сложный предназначена для позволит предотвратить необходимость самостоятельного управления сведениях сокета. Создать сокет "," файл "и" архив и затем начать отправку или получение данных путем вставки его в архив или извлечении его из архива. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), и [CSocket](../mfc/reference/csocket-class.md) управлять сведениями за кулисами.

Объект `CSocket` объект является объектом двух состояний: иногда асинхронной (обычно состояние) и иногда синхронные. Состояние асинхронного сокета может получать асинхронные уведомления из .NET framework. Тем не менее во время операции, такие как получение или отправка данных сокет становится синхронной. Это означает, что сокет будет больше не асинхронно получать уведомления до завершения синхронной операции. Так как она переключает режимы, можно например, выполните примерно следующим образом:

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

Если `CSocket` не были реализованы в виде двух состояний объекта, можно получать дополнительные уведомления для одного вида событий во время предыдущего уведомления обрабатывалась. Например, может появиться `OnReceive` уведомления при обработке `OnReceive`. В приведенном выше фрагменте кода, извлечение `str` из архива может привести к рекурсии. Путем переключения состояний, `CSocket` предотвращает рекурсии, предотвращая дополнительные уведомления. Общее правило состоит в уведомления, не в уведомлениях.

> [!NOTE]
> Объект `CSocketFile` можно также использовать как файл (ограниченная) без `CArchive` объекта. По умолчанию `CSocketFile` конструктора *bArchiveCompatible* параметр **TRUE**. Это указывает, что объект файла для использования с архивом. Чтобы использовать объект файла без архив, передайте **FALSE** в *bArchiveCompatible* параметра.

В режиме «архив compatible» `CSocketFile` объект обеспечивает более высокую производительность и уменьшает риск «взаимоблокировка». Взаимоблокировка возникает, когда отправки и получения сокеты ожидают друг друга или общий ресурс. Это может произойти, если `CArchive` объект работали с `CSocketFile` так, как с помощью `CFile` объекта. С помощью `CFile`, архива можно предположить, что при получении меньшее число байтов, чем она запрошена, конец файла был достигнут. С помощью `CSocketFile`, тем не менее, данные сообщение в зависимости; буфер может содержать несколько сообщений, поэтому получение меньше количества запрошенных байтов не подразумевает, что конец файла. Приложение не будет блокировать в данном случае, как это может быть с `CFile`, и может продолжить чтение сообщений из буфера, пока буфер пуст. [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) работать в `CArchive` полезны для мониторинга состояния буфера архива в этом случае.

Дополнительные сведения см. в разделе [сокеты Windows: Использование сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>См. также

[Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject::Serialize](../mfc/reference/cobject-class.md#serialize)
