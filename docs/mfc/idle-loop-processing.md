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
ms.openlocfilehash: 74ca89d91cf4e60b09a063551b526f177caed161
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624519"
---
# <a name="idle-loop-processing"></a>Обработка пустых циклов

Многие приложения выполняют длительную обработку "в фоновом режиме". Иногда для такой работы необходимо использовать многопоточность. Потоки содержат дополнительные издержки на разработку, поэтому их не рекомендуется использовать для простых задач, например для работы MFC в функции [OnIdle](reference/cwinthread-class.md#onidle) . В этой статье рассматривается обработка бездействия. Дополнительные сведения о многопоточности см. в [разделах о многопоточной](../parallel/multithreading-support-for-older-code-visual-cpp.md)работе.

Некоторые виды фоновой обработки выполняются в промежутки времени, когда пользователь не взаимодействует с приложением иным образом. В приложении, разработанном для операционной системы Microsoft Windows, приложение может выполнять обработку во время простоя, разбивая длительный процесс на множество небольших фрагментов. После обработки каждого фрагмента приложение передает управление выполнением в Windows с помощью цикла [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) .

В этой статье описываются два способа выполнения бездействия в приложении.

- Использование **PeekMessage** в главном цикле обработки сообщений MFC.

- Внедрение другого цикла **PeekMessage** в другое место в приложении.

## <a name="peekmessage-in-the-mfc-message-loop"></a><a name="_core_peekmessage_in_the_mfc_message_loop"></a>PeekMessage в цикле обработки сообщений MFC

В приложении, разработанном с помощью MFC, главный цикл обработки сообщений в `CWinThread` классе содержит цикл обработки сообщений, который вызывает API Win32 [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) . Этот цикл также вызывает `OnIdle` функцию члена `CWinThread` между сообщениями. Приложение может обрабатывать сообщения в этом времени простоя путем переопределения `OnIdle` функции.

> [!NOTE]
> `Run`, `OnIdle` и некоторые другие функции члена теперь являются членами класса, `CWinThread` а не класса `CWinApp` . Класс `CWinApp` является производным от `CWinThread`.

Дополнительные сведения о выполнении обработки простоя см. в разделе [OnIdle](reference/cwinthread-class.md#onidle) *справочника по MFC*.

## <a name="peekmessage-elsewhere-in-your-application"></a><a name="_core_peekmessage_elsewhere_in_your_application"></a>PeekMessage в любом расположении приложения

Другой метод выполнения процесса простоя в приложении включает внедрение цикла обработки сообщений в одну из функций. Этот цикл обработки сообщений очень похож на главный цикл обработки сообщений MFC, который находится в [CWinThread:: Run](reference/cwinthread-class.md#run). Это означает, что такой цикл в приложении, разработанном с помощью MFC, должен выполнять многие из тех же функций, что и основной цикл обработки сообщений. В следующем фрагменте кода демонстрируется написание цикла обработки сообщений, совместимого с MFC.

[!code-cpp[NVC_MFCDocView#8](codesnippet/cpp/idle-loop-processing_1.cpp)]

Этот код, внедренный в функцию, выполняет циклы до тех пор, пока выполняется обработка в режиме простоя. Внутри этого цикла вложенный цикл многократно вызывает `PeekMessage` . Пока этот вызов возвращает ненулевое значение, цикл вызывает метод `CWinThread::PumpMessage` для выполнения обычного преобразования сообщений и диспетчеризации. Несмотря на `PumpMessage` то, что документ не документирован, его исходный код можно проверить в файле срдкоре. cpp в каталоге \атлмфк\срк\мфк установки Visual C++.

После завершения внутреннего цикла внешний цикл выполняет обработку бездействия с одним или несколькими вызовами `OnIdle` . Первый вызов предназначен для целей MFC. Можно выполнять дополнительные вызовы для `OnIdle` выполнения собственной фоновой работы.

Дополнительные сведения о выполнении обработки простоя см. в разделе [OnIdle](reference/cwinthread-class.md#onidle) справочника по библиотеке MFC.

## <a name="see-also"></a>См. также раздел

[Общие разделы по MFC](general-mfc-topics.md)
