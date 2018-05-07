---
title: 'Сокеты Windows: Использование класса CAsyncSocket | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAsyncSocket
dev_langs:
- C++
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a96ccdd4ce5c49f18c12aa85060954fc97a3408b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Сокеты Windows. Использование класса CAsyncSocket
В этой статье объясняется, как использовать класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Имейте в виду, что этот класс инкапсулирует API Windows Sockets на очень низком уровне. `CAsyncSocket` предназначен для программистов, сетевое взаимодействие подробно известен, но требуется удобства обратных вызовов для уведомлений о событиях в сети. Исходя из-за этого предположения, эта статья содержит только базовые инструкции. Возможно, следует рассмотреть возможность использования `CAsyncSocket` Если действия для упрощения работы с нескольких сетевых протоколов в приложении MFC Windows Sockets, но не требуется пожертвовать гибкостью. Вам также может быть, можно получить более высокую эффективность запрограммировав дополнительные связи, напрямую самостоятельно чем удалось с помощью модели более общих класса `CSocket`.  
  
 `CAsyncSocket` документирован в *Справочник по библиотеке MFC*. Visual C++ также предоставляет спецификации Windows Sockets, расположенный в Windows SDK. Подробные сведения осталось вам. Visual C++ не предоставляет образец приложения для `CAsyncSocket`.  
  
 Если вы не высокой знаниями о сетевых подключений и простое решение, используйте класс [CSocket](../mfc/reference/csocket-class.md) с `CArchive` объекта. В разделе [Windows Sockets: с помощью сокетов с архивами](../mfc/windows-sockets-using-sockets-with-archives.md) для получения дополнительной информации.  
  
 В этой статье рассматриваются следующие действия:  
  
-   Создание и использование `CAsyncSocket` объекта.  
  
-   [Ваши обязанности с CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Создание и использование объекта CAsyncSocket  
  
#### <a name="to-use-casyncsocket"></a>Чтобы использовать CAsyncSocket  
  
1.  Создать [CAsyncSocket](../mfc/reference/casyncsocket-class.md) объекта и использовать объект для создания базового **СОКЕТА** обработки.  
  
     Создание сокета соответствует шаблону MFC конструкции два этапа.  
  
     Пример:  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     - или -  
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     Первый конструктор выше создает `CAsyncSocket` объект в стеке. Второй конструктор создает `CAsyncSocket` в куче. Первый [создать](../mfc/reference/casyncsocket-class.md#create) выше вызов использует параметры по умолчанию для создания потока сокета. Второй **создать** вызов создает сокет датаграммы с указанного порта и адрес. (Можно использовать любой **создать** версии независимо от выбранного способа построения.)  
  
     Параметры для **создать** являются:  
  
    -   «Порт»: короткое целое число.  
  
         Для сокета сервера необходимо указать порт. Для сокета клиента обычно принять значение по умолчанию для этого параметра, которое позволяет выбрать порт сокеты Windows.  
  
    -   Тип сокета: **SOCK_STREAM** (по умолчанию) или **SOCK_DGRAM**.  
  
    -   Соединение «адрес», например «ftp.microsoft.com» или «128.56.22.8».  
  
         Это ваш адрес протокола Интернета (IP) в сети. Вероятно, всегда будет использовать значение по умолчанию для этого параметра.  
  
     Термины «порт» и «адрес сокета» приведены в [Windows Sockets: порты и адреса сокета](../mfc/windows-sockets-ports-and-socket-addresses.md).  
  
2.  Если клиент является сокета, подключиться к серверу объект сокета сокета, используя [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect).  
  
     - или -  
  
     Если сокета сервера, установите сокет для приема (с [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) для попыток подключения от клиента. При получении запроса на подключение, примите его с [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
     После принятия запроса на подключение, вы можете выполнить такие задачи, как проверка паролей.  
  
    > [!NOTE]
    >  **Accept** функции-члена принимает ссылку на новый, пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода **Accept**. Если этот объект сокета выходит за пределы области, закрывает соединение. Не вызывайте **создать** для этого нового объекта сокета. Например, см. в статье [Windows Sockets: последовательность операций](../mfc/windows-sockets-sequence-of-operations.md).  
  
3.  Выполнять обмен данными с другими сокетов, вызывая `CAsyncSocket` функций-членов объектов которые инкапсулируют функции Windows Sockets API.  
  
     См. в спецификации Windows Sockets и класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md) в *Справочник по библиотеке MFC*.  
  
4.  Уничтожить `CAsyncSocket` объекта.  
  
     При создании объекта сокета в стеке, его деструктор вызывается при содержащего функция выходит за пределы области. При создании сокета объекта в куче с помощью **новый** оператор, вы несете ответственность за использование **удалить** оператор для уничтожения объекта.  
  
     Деструктор вызывает объект [закрыть](../mfc/reference/casyncsocket-class.md#close) функции-члена до уничтожения объекта.  
  
 В качестве примера данной последовательности в коде (фактически для `CSocket` объекта), в разделе [Windows Sockets: последовательность операций](../mfc/windows-sockets-sequence-of-operations.md).  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> Ваши обязанности с CAsyncSocket  
 При создании объекта класса [CAsyncSocket](../mfc/reference/casyncsocket-class.md), объект инкапсулирует Windows **СОКЕТА** обработки и предоставляет операции для этого дескриптора. При использовании `CAsyncSocket`, необходимо обработать все проблемы, которые могут появиться при непосредственном использовании API-интерфейса. Пример:  
  
-   Сценарии «Блокировка».  
  
-   Байтов порядок различия между отправляющим и принимающим машины.  
  
-   Преобразование между Юникодом и многобайтовой набора строк (MBCS).  
  
 Для определения этих терминов и Дополнительные сведения см. в разделе [Windows Sockets: блокирование](../mfc/windows-sockets-blocking.md), [Windows Sockets: порядок байтов](../mfc/windows-sockets-byte-ordering.md), [Windows Sockets: преобразование строки](../mfc/windows-sockets-converting-strings.md) .  
  
 Несмотря на эти проблемы класса **CAsycnSocket** может быть целесообразно для вас, если приложение требует гибкости и управления, можно получить. Если нет, можно использовать класс `CSocket` вместо него. `CSocket` скрывает множество сведений от вас: ИТ направляет сообщения во время блокирующих вызовов Windows и предоставляет доступ к `CArchive`, который управляет различия порядка байтов и преобразования строк для вас.  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Фон](../mfc/windows-sockets-background.md)  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)

