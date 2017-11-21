---
title: "Сокеты Windows: Работа сокетов с архивами | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd387ad53bc02995c5be76819e9db1f2f7d6edbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Сокеты Windows. Работа сокетов с архивами
В этой статье объясняется, как [CSocket](../mfc/reference/csocket-class.md) объекта, [CSocketFile](../mfc/reference/csocketfile-class.md) объекта и [CArchive](../mfc/reference/carchive-class.md) объекта объединяются и упрощают отправку и получение данных с помощью Windows Сокет.  
  
 Статья [Windows Sockets: пример из сокетов с использованием архивов](../mfc/windows-sockets-example-of-sockets-using-archives.md) представляется **PacketSerialize** функции. Объект архива в **PacketSerialize** пример работает почти как архив объекта, передаваемого MFC [сериализации](../mfc/reference/cobject-class.md#serialize) функции. Основные отличается для сокетов, архив присоединен не стандарту [CFile](../mfc/reference/cfile-class.md) (обычно связана с файла на диске) объекта а `CSocketFile` объекта. Вместо того чтобы подключаться в файл на диске, `CSocketFile` соединения объекта `CSocket` объекта.  
  
 Объект `CArchive` управляет буфером. При заполнении буфера хранения архива (отправка), связанный с ним `CFile` объекта записывает содержимое буфера. Очистка буфера архив подключенное к разъему соответствует отправку сообщения. При переполнении буфера архив загрузка (получение) `CFile` объекта остановлено считывание, пока буфер не освободится.  
  
 Класс `CSocketFile` является производным от `CFile`, но не поддерживает [CFile](../mfc/reference/cfile-class.md) члена функции, такие как функции размещения (`Seek`, `GetLength`, `SetLength`и так далее), блокировка функции () `LockRange`, `UnlockRange`), или `GetPosition` функции. Все [CSocketFile](../mfc/reference/csocketfile-class.md) объекта необходимо сделать — записи или чтения последовательности байтов или из связанного `CSocket` объекта. Так как файл не используется, операций, таких как `Seek` и `GetPosition` не имеет смысла. `CSocketFile`является производным от `CFile`, поэтому он обычно наследует все эти функции-члены. Чтобы это предотвратить, неподдерживаемое `CFile` функции-члены переопределяются в `CSocketFile` создаст [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).  
  
 `CSocketFile` Объект вызывает член функции его `CSocket` объект для отправки и получения данных.  
  
 На следующем рисунке показана отношения между этими объектами на обеих сторонах связи.  
  
 ![CArchive, CSocketFile и CSocket](../mfc/media/vc38ia1.gif "vc38ia1")  
CArchive, CSocketFile и CSocket  
  
 Это сложность предназначена для экранировать вас от необходимости самостоятельного управления сведения сокета. Создание сокета, файл и архив и затем начните отправки или получения данных путем вставки его в архив или извлечения из архива. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), и [CSocket](../mfc/reference/csocket-class.md) управления информацией в фоновом.  
  
 Объект `CSocket` объект является объектом два состояния: иногда асинхронной (обычном состоянии) и иногда синхронной. Состояние асинхронного сокета может получать асинхронные уведомления от платформы. Однако при выполнении операции, такие как получение или отправка данных сокета становится синхронной. Это означает, что сокет будет дальнейшая асинхронно получать уведомления до завершения синхронной операции. Поскольку переключении режимов, можно например, выполнять примерно следующим образом:  
  
 [!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]  
  
 Если `CSocket` не были реализованы как объект два состояния, могут быть доступны для получения дополнительных уведомлений для одного типа событий во время обработки предыдущего уведомления. Например, может появиться `OnReceive` уведомления при обработке `OnReceive`. В приведенном выше фрагменте кода извлечение `str` из архива может привести к рекурсии. С помощью переключения состояния, `CSocket` предотвращает рекурсии, так как дополнительные уведомления. Общее правило — не появляются уведомления в пределах уведомления.  
  
> [!NOTE]
>  Объект `CSocketFile` также может использоваться как файл (ограниченная) без `CArchive` объекта. По умолчанию `CSocketFile` конструктора `bArchiveCompatible` параметр **TRUE**. Это указывает, что объект файла для использования в архив. Чтобы использовать объект файла без архив, передайте **FALSE** в `bArchiveCompatible` параметра.  
  
 В режиме «compatible архива» `CSocketFile` объект обеспечивает более высокую производительность и уменьшает опасность «взаимоблокировка». Взаимоблокировка возникает, когда сокетам отправки и получения ожидают друг друга или Ожидание общих ресурсов. Подобная ситуация может возникнуть, если `CArchive` объекта работали с `CSocketFile` так, как и с `CFile` объекта. С `CFile`, архива можно предположить, что при получении меньше байтов, чем она запрошена, конец файла был достигнут. С `CSocketFile`, тем не менее, данные на основе сообщений; буфер может содержать несколько сообщений, поэтому получение меньше, чем количество запрошенных байтов не означает конец файла. Приложения, не блокируют в данном случае что он может с `CFile`, и может продолжать чтение из буфера сообщений, пока буфер пуст. [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) функционировать в `CArchive` полезны для мониторинга состояния буфера архива в таком случае.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)   
 [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)

