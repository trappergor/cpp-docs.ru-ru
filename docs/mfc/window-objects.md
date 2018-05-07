---
title: Объекты окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63b8d8dbde679d030eddd77fae6ca1fab519fdac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="window-objects"></a>Объекты окон
MFC предоставляет класс [CWnd](../mfc/reference/cwnd-class.md) для инкапсуляции `HWND` дескриптор окна. `CWnd` Является объектом окна C++, отличающийся от `HWND` , представляющий Windows, но содержащий его окно. Используйте `CWnd` для формирования собственных дочернее окно классы, или воспользуйтесь одним из многих классов MFC на основе `CWnd`. Класс `CWnd` является базовым классом для всех окон, включая окна фрейма, диалоговые окна, дочерних окон, элементов управления и панели элементов управления, таких как панели инструментов. Хорошо понимать [связь между объектом окна C++ и HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) очень важно для эффективной программирование с использованием MFC.  
  
 MFC предоставляет некоторые функциональные возможности по умолчанию и управления windows, но можно создать собственный класс, от `CWnd` и использовать его функций-членов для настройки указанных функций. Вы можете создавать дочерние окна, создав `CWnd` объекта и вызвать его [создать](../mfc/reference/cwnd-class.md#create) члена функции, а затем настроить с помощью дочерних окон `CWnd` функции-члены. Можно внедрять объектов, производных от [CView](../mfc/reference/cview-class.md), например формы представления или представления в виде дерева, в окне фрейма. И может поддерживать несколько представлений документов через разделитель областей, предоставляемые классом [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).  
  
 Каждый объект, производный от класса `CWnd` содержит схему сообщений, через который можно сопоставить сообщения Windows или идентификаторы команд для собственных обработчиков.  
  
 Общие литература на программирование для Windows является ценным ресурсом для изучения способов применения `CWnd` функции-члены, которые инкапсулируют `HWND` API-интерфейсы.  
  
## <a name="functions-for-operating-on-a-cwnd"></a>Функции для работы с CWnd  
 `CWnd` и его [производные классы окон](../mfc/derived-window-classes.md) предоставляют конструкторы, деструкторы и функции-члены для инициализации объекта, Создание базовых структур Windows и доступ к инкапсулированный `HWND`. `CWnd` также предоставляет функции-члены, инкапсулирующие API-интерфейсов Windows для отправки сообщений, доступа к состоянию окна, преобразование координат, обновление, прокрутка, доступ к буферу обмена и многие другие задачи. Большинство интерфейсов API управления окнами Windows, принимающих `HWND` аргумент инкапсулированы в виде функций-членов `CWnd`. Имена функций и их параметры сохраняются в `CWnd` функции-члена. Для получения сведений об API-интерфейсы Windows, инкапсулированных в `CWnd`, см. класс [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="cwnd-and-windows-messages"></a>Сообщения Windows и CWnd  
 Одно из основных целей `CWnd` для предоставления интерфейса для обработки сообщений Windows, таких как `WM_PAINT` или `WM_MOUSEMOVE`. Многие из функций-членов `CWnd` являются обработчики для стандартных сообщений, начинающихся с идентификатором **afx_msg** и префикс «On», такие как `OnPaint` и **OnMouseMove**. [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md) рассматриваются сообщений и подробно обработки сообщений. Там сведения одинаково применимо для платформы windows, так и создать самостоятельно для особых целей.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Связь между объектом окна C++ и HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Производные классы окон](../mfc/derived-window-classes.md)  
  
-   [Создание окон](../mfc/creating-windows.md)  
  
-   [Уничтожение объектов окон](../mfc/destroying-window-objects.md)  
  
-   [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Работа с объектами окон](../mfc/working-with-window-objects.md)  
  
-   [Контексты устройств](../mfc/device-contexts.md): сделать независимых графических устройств Windows  
  
-   [Графические объекты](../mfc/graphic-objects.md): перья, кисти, шрифты, растровые изображения, палитр, областей  
  
## <a name="see-also"></a>См. также  
 [Windows](../mfc/windows.md)

