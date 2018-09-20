---
title: Windows | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], window
- windows [MFC]
- MFC, windows
- window objects [MFC], MFC Framework
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 664afc2d842a7072ed41d579939e530e01c6e33f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431779"
---
# <a name="windows"></a>Windows

Этот сборник статей рассматриваются объекты окна платформы MFC. Все окна MFC являются производными от класса [CWnd](../mfc/reference/cwnd-class.md), включая окна фрейма, представлений, окон и элементов управления.

Первая группа статей описывает [объектов окна](../mfc/window-objects.md) в целом. Ссылки на эту группу, общие сведения об объектах окно C++, как они инкапсулируют `HWND`, и как их использовать при создании собственных windows, таких как дочерние окна.

Вторая группа статей описывает [окон с фреймами](../mfc/frame-windows.md)— windows, которые добавляют рамку вокруг содержимого — в частности. Ссылки на эту группу, сведения об управлении платформой MFC, окон фреймов и содержимое фрейма, включая панели элементов управления и представления.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

*Разделы, посвященные объектов окна в целом*

- [Объекты окон](../mfc/window-objects.md)

- [Связь между C++ обрабатывает объекты окон и HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [Производные классы окон](../mfc/derived-window-classes.md)

- [Создание объектов-окон](../mfc/creating-windows.md)

- [Уничтожение объектов окон](../mfc/destroying-window-objects.md)

- [Регистрация классов «window»](../mfc/registering-window-classes.md)

- [Работа с объектами окон](../mfc/working-with-window-objects.md)

- [Контексты устройств](../mfc/device-contexts.md): объекты, которые делают Windows Рисование аппаратно независимых

- [Графические объекты](../mfc/graphic-objects.md): перья, кисти, шрифты, растровые изображения, палитр, регионах

*Разделы окна фрейма*

- [Окна фрейма](../mfc/frame-windows.md): объекты окон, которые предоставляют кадров

- [Окна фрейма и представления](../mfc/frame-windows.md)

- [Классы окна фрейма](../mfc/frame-window-classes.md)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

- [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [Окон фрейма](../mfc/what-frame-windows-do.md)

- [Использование окон фрейма](../mfc/using-frame-windows.md)

- [Управление MD/дочерними окнами (окно MDICLIENT)](../mfc/managing-mdi-child-windows.md)

- [Управление меню, панелей элементов управления и ускорителями](../mfc/managing-menus-control-bars-and-accelerators.md)

- [CFrameWnd](../mfc/reference/cframewnd-class.md)

- [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)

- [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)

- [Использование представлений](../mfc/using-views.md)

- [Несколько типов документов, представлений и фрейма Windows (окна разделителей)](../mfc/multiple-document-types-views-and-frame-windows.md)

- [Сообщения (карты и функции обработчика)](../mfc/messages.md)

*Создавать и уничтожать Windows*

- [Общая последовательность создания окна](../mfc/general-window-creation-sequence.md)

- [Уничтожения объектов окон](../mfc/destroying-window-objects.md)

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

- [Уничтожения окна фрейма](../mfc/destroying-frame-windows.md)

*Создание разделителя Windows*

- [Создание окна разделителей](../mfc/multiple-document-types-views-and-frame-windows.md)

*Управление Windows дочерних и текущее представление*

- [Управление дочерними окнами MDI](../mfc/managing-mdi-child-windows.md)

- [Управление текущим представлением](../mfc/managing-the-current-view.md)

- [Управление меню, панелей элементов управления и ускорителями](../mfc/managing-menus-control-bars-and-accelerators.md)

*Работа с контексты устройств и стили окна*

- [Использовать перья и другие графические объекты в контексте устройства](../mfc/graphic-objects.md)

- [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)<br/>
[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Панели инструментов](../mfc/toolbars.md)<br/>
[Строки состояния](../mfc/status-bars.md)<br/>
[Диалоговые панели](../mfc/dialog-bars.md)

