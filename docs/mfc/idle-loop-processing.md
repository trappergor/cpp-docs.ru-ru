---
title: Обработка пустых циклов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d66983eb915c856ecf52e225b71151359a499b4b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354905"
---
# <a name="idle-loop-processing"></a>Обработка пустых циклов
Во многих приложениях выполнения продолжительной обработки «в фоновом режиме». Иногда вопросы производительности могут предписывать Использование многопоточности для такой работы. Потоки включают дополнительные издержки, поэтому их не рекомендуется для простых задач вроде рабочего времени простоя, выполняющий MFC в [OnIdle](../mfc/reference/cwinthread-class.md#onidle) функции. Эта статья посвящена обработка бездействия. Дополнительные сведения о многопоточности см [многопоточность](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Некоторые виды фоновой обработки, соответствующим образом выполняется через промежутки времени, которые пользователь в противном случае не взаимодействует с приложением. В приложении, разработанном для операционной системы Microsoft Windows приложение может выполнять обработку времени простоя, разделив длительным процессом на многих небольших фрагментов. После обработки каждого фрагмента, приложение передает управление выполнения Windows с помощью [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) цикла.  
  
 В этой статье описываются два способа простоя обработки в приложении:  
  
-   С помощью **PeekMessage** в MFC основной цикл обработки сообщений.  
  
-   Внедрение другой **PeekMessage** цикл в другом месте в приложении.  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> PeekMessage в цикл обработки сообщений MFC  
 В приложение, разработанное с MFC, цикл основного сообщения в `CWinThread` класс содержит цикл обработки сообщений, который вызывает [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Win32 API. Это также цикла вызовы `OnIdle` функцию-член `CWinThread` между сообщениями. Приложение может обработать в это время простоя, переопределив `OnIdle` функции.  
  
> [!NOTE]
>  **Запустите**, `OnIdle`, и некоторые другие функции-члены теперь являются членами класса `CWinThread` , а не класса `CWinApp`. Класс `CWinApp` является производным от `CWinThread`.  
  
 Дополнительные сведения о выполнении обработка бездействия. в разделе [OnIdle](../mfc/reference/cwinthread-class.md#onidle) в *Справочник по библиотеке MFC*.  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage в другом месте в приложении  
 Другой способ выполнения простоя обработки в приложении включает в себя внедрение цикл обработки сообщений в одной из функций. Этот цикл обработки сообщений очень похожа на MFC основной цикл обработки сообщений, в [CWinThread::Run](../mfc/reference/cwinthread-class.md#run). Это означает, что цикл в приложение, разработанное с MFC должен выполнять многие функции основной цикл обработки сообщений. В следующем фрагменте кода демонстрируется запись цикл обработки сообщений, совместимый с MFC:  
  
 [!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]  
  
 Этот код, внедренный в функции, цикл выполняется до тех пор, пока имеется обработка простоя для выполнения. В этом цикле вложенного цикла многократно вызывает **PeekMessage**. При условии, что этот вызов возвращает ненулевое значение, цикл вызывает `CWinThread::PumpMessage` для выполнения преобразования обычного сообщения и диспетчеризации. Несмотря на то что `PumpMessage` не задокументирован, можно просмотреть его исходный код в файле ThrdCore.Cpp в каталоге \atlmfc\src\mfc установки Visual C++.  
  
 Один раз внутренний цикл завершается, внешний цикл выполняет обработку бездействия с одного или нескольких вызовов `OnIdle`. Сначала вызывается для целей MFC. Можно выполнять дополнительные вызовы `OnIdle` для фоновой работы.  
  
 Дополнительные сведения о выполнении обработка бездействия. в разделе [OnIdle](../mfc/reference/cwinthread-class.md#onidle) в справочнике по библиотеке MFC.  
  
## <a name="see-also"></a>См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)

