---
title: Windows | Документы Microsoft
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
ms.openlocfilehash: 88ba41b7bb921cc2834b4d45712be768b2d19f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384469"
---
# <a name="windows"></a>Windows
Этот сборник статей рассматриваются объекты окон в платформе MFC. Все окна MFC является производным от класса [CWnd](../mfc/reference/cwnd-class.md), включая окна фрейма, представления, диалоговые окна и элементов управления.  
  
 Первая группа статей описывает [объекты окон](../mfc/window-objects.md) в целом. Ссылки на эту группу, общие сведения о C++ объекты окон, как они инкапсулируют HWND и как их использовать при создании собственных windows, таких как дочерние окна.  
  
 Вторая группа статьи описывается [окна фрейма](../mfc/frame-windows.md)— windows, которые помещают рамку вокруг содержимого — в частности. Ссылки на эту группу, сведения о том, как платформа MFC управляет фреймов и содержимое фрейма, включая панели элементов управления и представления.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
 *Разделы, посвященные объекты окон в целом*  
  
-   [Объекты окон](../mfc/window-objects.md)  
  
-   [Связь между C++ обрабатывает объекты окон и HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Производные классы окон](../mfc/derived-window-classes.md)  
  
-   [Создание объектов-окон](../mfc/creating-windows.md)  
  
-   [Уничтожение объектов окон](../mfc/destroying-window-objects.md)  
  
-   [Регистрация классов «окон»](../mfc/registering-window-classes.md)  
  
-   [Работа с объектами окон](../mfc/working-with-window-objects.md)  
  
-   [Контексты устройств](../mfc/device-contexts.md): объекты, которые сделать рисунок Windows аппаратно независимых  
  
-   [Графические объекты](../mfc/graphic-objects.md): перья, кисти, шрифты, растровые изображения, палитр, областей  
  
 *Разделы окна фрейма*  
  
-   [Окна фрейма](../mfc/frame-windows.md): окно объектов, предоставляющих кадров  
  
-   [Окна фрейма и представления](../mfc/frame-windows.md)  
  
-   [Классы окна фрейма](../mfc/frame-window-classes.md)  
  
-   [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)  
  
-   [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Окон фрейма](../mfc/what-frame-windows-do.md)  
  
-   [Использование окон фрейма](../mfc/using-frame-windows.md)  
  
-   [Управление окнами MD-потомки (окно MDICLIENT)](../mfc/managing-mdi-child-windows.md)  
  
-   [Управление меню, панелей элементов управления и ускорителями](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [CFrameWnd](../mfc/reference/cframewnd-class.md)  
  
-   [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
  
-   [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
  
-   [Использование представлений](../mfc/using-views.md)  
  
-   [Несколько типов документов, представлений и фреймов (разделитель windows)](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Сообщения (карты и функции обработчика)](../mfc/messages.md)  
  
 *Создание и уничтожение Windows*  
  
-   [Общая последовательность создания окна](../mfc/general-window-creation-sequence.md)  
  
-   [Удалить объекты окон](../mfc/destroying-window-objects.md)  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
-   [Уничтожения окна фрейма](../mfc/destroying-frame-windows.md)  
  
 *Создание окна разделителей*  
  
-   [Создание окна разделителей](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
 *Управление дочерними окнами и текущее представление*  
  
-   [Управление дочерними окнами MDI](../mfc/managing-mdi-child-windows.md)  
  
-   [Управление текущим представлением](../mfc/managing-the-current-view.md)  
  
-   [Управление меню, панелей элементов управления и ускорителями](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 *Работа с контексты устройств и стили окна*  
  
-   [Используйте перья и другие графические объекты в контексте устройств](../mfc/graphic-objects.md)  
  
-   [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Панели инструментов](../mfc/toolbars.md)   
 [Строки состояния](../mfc/status-bars.md)   
 [Диалоговые панели](../mfc/dialog-bars.md)

