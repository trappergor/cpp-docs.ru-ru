---
title: Окна фрейма
ms.date: 11/04/2016
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame windows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
ms.openlocfilehash: 09db7bab392778297f17c14f7bb807f91af4d896
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619938"
---
# <a name="frame-windows"></a>Окна фрейма

Если приложение выполняется в группе Windows, пользователь взаимодействует с документами, отображаемыми в окнах фрейма. Окном фрейма документа состоит из двух основных компонентов: рамки и содержимое, на которые он кадры. Может быть окном фрейма документа [однооконный интерфейс](../mfc/sdi-and-mdi.md) окна фрейма (SDI) или [многодокументного интерфейса](../mfc/sdi-and-mdi.md) дочернего окна (интерфейса MDI). Windows управляет большей частью взаимодействие пользователя с окном фрейма: перемещение и изменение размеров окна, закройте приложение и минимизировать и максимально увеличить его. Управление содержимое внутри рамки.

## <a name="frame-windows-and-views"></a>Windows фрейма и представления

Платформа MFC использует окна фрейма для хранения представлений. Эти два компонента — страницы и содержимое, представляются и управляются два различных классов в MFC. Класс окна фрейма управляет кадр и класс представления управляет содержимое. В окне представления является дочерним фрейма окна. Рисование и вмешательстве пользователя с документом выполняются в клиентской области представления, не клиентской области окна фрейма. Окна фрейма предоставляет видимым рамку вокруг представления, а заголовок окна и стандартное окно элементов управления, например элемент управления меню, кнопки, чтобы свернуть или развернуть окно и элементы управления для изменения размера окна. «Содержимое» состоит из клиентской области окна, которой полностью занятую дочернее окно — представление. На рисунке показана связь между окна фрейма и представления.

![Представление окна фрейма](../mfc/media/vc37fx1.gif "vc37fx1") окна фрейма и представления

## <a name="frame-windows-and-splitter-windows"></a>Кадр Windows и Windows разделителя

Другой распространенных упорядочение — для окна фрейма, обведите несколько представлений, обычно с помощью [окно с разделителем](../mfc/multiple-document-types-views-and-frame-windows.md). В окне разделителя занимается клиентской области окна фрейма окна разделителя, который в свою очередь имеет несколько дочерних окон, панелей, которые являются представлениями вызывается.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

**Окна фрейма общие разделы**

- [Объекты окон](../mfc/window-objects.md)

- [Классы окна фрейма](../mfc/frame-window-classes.md)

- [Классы окна фрейма, созданные с помощью мастера приложений](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

- [Окон фрейма](../mfc/what-frame-windows-do.md)

**Разделы об использовании Windows кадра**

- [Использование окон фрейма](../mfc/using-frame-windows.md)

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

- [Уничтожение окон фрейма](../mfc/destroying-frame-windows.md)

- [Управление дочерними окнами MDI](../mfc/managing-mdi-child-windows.md)

- [Управление текущим представлением](../mfc/managing-the-current-view.md) фрейм окна, который содержит несколько представлений

- [Управление меню, панелей элементов управления и ускорителями (другие объекты, которые совместно используют пространство окна фрейма)](../mfc/managing-menus-control-bars-and-accelerators.md)

**Разделы по возможности специальные фрейма окна**

- [Перетаскивание файлов](../mfc/dragging-and-dropping-files-in-a-frame-window.md) из проводника или диспетчер файлов в окне фрейма

- [Реагирование на динамический обмен данными (DDE)](../mfc/responding-to-dynamic-data-exchange-dde.md)

- [Полумодальные состояния: контекстные справки Windows (Оркестрация других действий окна)](../mfc/orchestrating-other-window-actions.md)

- [Полумодальные состояния: печати и предварительного просмотра (Оркестрация других действий окна)](../mfc/orchestrating-other-window-actions.md)

**Разделы, посвященные другие виды Windows**

- [Использование представлений](../mfc/using-views.md)

- [Диалоговые окна](../mfc/dialog-boxes.md)

- [Элементы управления](../mfc/controls-mfc.md)

## <a name="see-also"></a>См. также

[Windows](../mfc/windows.md)

