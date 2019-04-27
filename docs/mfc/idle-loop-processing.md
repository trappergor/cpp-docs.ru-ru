---
title: Обработка пустых циклов
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
ms.openlocfilehash: 0d0e3fcba9ce447ec359958fc5ed59c6d596dd7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219494"
---
# <a name="idle-loop-processing"></a>Обработка пустых циклов

Многие приложения выполняют продолжительной обработки «в фоновом режиме.» Иногда вопросы производительности определяют использование многопоточности для такой работы. Потоки включают в себя дополнительные издержки, поэтому их не рекомендуется для простых задач вроде рабочего времени простоя, которую выполняет MFC в [OnIdle](../mfc/reference/cwinthread-class.md#onidle) функции. Эта статья посвящена обработка бездействия. Дополнительные сведения о многопоточности см [разделах, посвященных многопоточности](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Некоторые виды фоновой обработки, соответствующим образом выполняется во время интервалов, которые пользователь в противном случае не взаимодействует с приложением. В приложении, разработанном для операционной системы Microsoft Windows приложение может выполнять обработку времени простоя, разделив длительное время на много небольших фрагментов. После обработки каждого фрагмента, приложение возвращает управление выполнением в Windows с помощью [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) цикла.

В этой статье описываются два способа простоя обработки в приложении:

- С помощью **PeekMessage** в MFC основной цикл обработки сообщений.

- Внедрение другой **PeekMessage** цикл в другом месте в приложении.

##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> PeekMessage в цикл обработки сообщений MFC

В приложении, разработанном с MFC, цикл основного сообщения `CWinThread` класс содержит цикл обработки сообщений, который вызывает [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) Win32 API. Это также цикл вызовы `OnIdle` функцию-член `CWinThread` между сообщениями. Приложение может обработать в это время простоя, переопределив `OnIdle` функции.

> [!NOTE]
>  `Run`, `OnIdle`, и некоторые другие функции-члены теперь являются членами класса `CWinThread` , а не класса `CWinApp`. Класс `CWinApp` является производным от `CWinThread`.

Дополнительные сведения о выполнении обработка бездействия, см. в разделе [OnIdle](../mfc/reference/cwinthread-class.md#onidle) в *Справочник по библиотеке MFC*.

##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage в другом месте в приложении

Другой способ выполнения простоя обработки в приложения включает в себя внедрение цикл обработки сообщений в нужную функцию. Этот цикл обработки сообщений очень похожа на MFC основной цикл обработки сообщений, в [CWinThread::Run](../mfc/reference/cwinthread-class.md#run). Это означает, что цикл в приложении, разработанном с MFC необходимо выполнить многие функции, как основной цикл обработки сообщений. В следующем фрагменте кода демонстрируется запись цикл обработки сообщений, совместимый с MFC:

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

Этот код, внедренный в функцию, цикл выполняется до тех пор, пока выполняется простоя для выполнения. Внутри этой петли, вложенными циклами раз за разом вызывает `PeekMessage`. До тех пор, пока этот вызов возвращает ненулевое значение, цикла вызывает `CWinThread::PumpMessage` для выполнения преобразования обычного сообщения и диспетчеризации. Несмотря на то что `PumpMessage` не задокументирован, можно просмотреть его исходный код в файле ThrdCore.Cpp в каталоге \atlmfc\src\mfc установки Visual C++.

Один раз внутренний цикл завершается, внешний цикл выполняет обработку бездействия с помощью одного или нескольких вызовов к `OnIdle`. Первый вызов направляется в целях MFC. Может отправлять дополнительные вызовы `OnIdle` сделать фонового потока.

Дополнительные сведения о выполнении обработка бездействия, см. в разделе [OnIdle](../mfc/reference/cwinthread-class.md#onidle) справочника по библиотеке MFC.

## <a name="see-also"></a>См. также

[Общие разделы по MFC](../mfc/general-mfc-topics.md)
