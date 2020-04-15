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
ms.openlocfilehash: 9579d4bb8768b0227453af401d6fdc8a8bd482b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376012"
---
# <a name="idle-loop-processing"></a>Обработка пустых циклов

Многие приложения выполняют длительную обработку "в фоновом режиме". Иногда соображения производительности диктуют использование многопоточности для такой работы. Темы включают дополнительные накладные расходы на разработку, поэтому они не рекомендуются для простых задач, таких как работа в простое время, которую MFC выполняет в функции [OnIdle.](../mfc/reference/cwinthread-class.md#onidle) Эта статья посвящена обработке простоя. Для получения дополнительной [информации](../parallel/multithreading-support-for-older-code-visual-cpp.md)о многопоточности см.

Некоторые виды фоновой обработки надлежащим образом выполняются в интервалах, которые пользователь не взаимодействует с приложением. В приложении, разработанном для операционной системы Microsoft Windows, приложение может выполнять обработку простоя, разделяя длительный процесс на множество мелких фрагментов. После обработки каждого фрагмента приложение дает управление выполнением Windows с помощью цикла [PeekMessage.](/windows/win32/api/winuser/nf-winuser-peekmessagew)

В этой статье объясняется два способа обработки простоя в приложении:

- Использование **PeekMessage** в основной цикл сообщения MFC.

- Встраивание другого цикла **PeekMessage** в другое место в приложении.

## <a name="peekmessage-in-the-mfc-message-loop"></a><a name="_core_peekmessage_in_the_mfc_message_loop"></a>PeekMessage в петле сообщений MFC

В приложении, разработанном с MFC, `CWinThread` основной цикл сообщений в классе содержит цикл сообщений, который вызывает [PikMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) Win32 API. Этот цикл также `OnIdle` вызывает `CWinThread` функцию члена между сообщениями. Приложение может обрабатывать сообщения в это простое время, переопределяя функцию. `OnIdle`

> [!NOTE]
> `Run`, `OnIdle`и некоторые другие функции `CWinThread` члена в `CWinApp`настоящее время члены класса, а не класса. Класс `CWinApp` является производным от `CWinThread`.

Для получения дополнительной информации о выполнении простаивающей обработки, см. [OnIdle](../mfc/reference/cwinthread-class.md#onidle) в *Ссылке MFC*.

## <a name="peekmessage-elsewhere-in-your-application"></a><a name="_core_peekmessage_elsewhere_in_your_application"></a>PeekMessage в другом месте в вашем приложении

Другой метод выполнения простоя обработки в приложении включает в себя встраивание цикла сообщений в одну из ваших функций. Этот цикл сообщений очень похож на основной цикл сообщений MFC, найденный в [CWinThread::Run](../mfc/reference/cwinthread-class.md#run). Это означает, что такой цикл в приложении, разработанном с MFC, должен выполнять многие из тех же функций, что и основной цикл сообщений. Следующий фрагмент кода демонстрирует написание цикла сообщений, совместимого с MFC:

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

Этот код, встроенный в функцию, циклов до тех пор, как есть простая обработка делать. В пределах этого цикла вложенный цикл неоднократно вызывает. `PeekMessage` До тех пор, пока этот вызов возвращает `CWinThread::PumpMessage` значение ненулевого значения, цикл требует выполнения нормального перевода сообщений и отправки. Несмотря `PumpMessage` на отсутствие документов, вы можете изучить его исходный код в файле ThrdCore.Cpp в каталоге установки Visual C' mfc.

Как только внутренняя петля заканчивается, внешняя `OnIdle`петля выполняет обработку простоя с одним или несколько вызовами. Первый звонок предназначен для целей МФЦ. Вы можете сделать `OnIdle` дополнительные звонки, чтобы сделать свою собственную фоновую работу.

Для получения дополнительной информации о выполнении простаивающей обработки, см. [OnIdle](../mfc/reference/cwinthread-class.md#onidle) в библиотеке Ссылка MFC.

## <a name="see-also"></a>См. также раздел

[Общие темы МФЦ](../mfc/general-mfc-topics.md)
