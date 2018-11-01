---
title: Создание новых документов, окон и представлений
ms.date: 11/04/2016
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
ms.openlocfilehash: 20bc94c7a688d3cf88fa89fff060ab155d327606
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643902"
---
# <a name="creating-new-documents-windows-and-views"></a>Создание новых документов, окон и представлений

Следующих снимках экрана обзора процесса создания документов, представлений и фреймов. Другие статьи, посвященные участвующие объекты приводятся подробные сведения.

По завершении этого процесса совместно действующих объектов существует и сохранения указателей на друг с другом. Ниже приведена последовательность, в которой создаются объекты. Вы можете следовать последовательности из рис на рис.

![Последовательность создания документа](../mfc/media/vc387l1.gif "vc387l1") последовательности в Создание документа

![Последовательность создания окна фрейма](../mfc/media/vc387l2.png "vc387l2") последовательность создания окна фрейма

![Последовательность создания представления](../mfc/media/vc387l3.gif "vc387l3") последовательности в создании представления

Сведения о как платформа Инициализирует новый документ, представления и окна фрейма объектов, см. в разделе классы [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) справочника по библиотеке MFC. Также см. в разделе [технические 22 Примечание](../mfc/tn022-standard-commands-implementation.md), где объясняется процесс создания и инициализации дополнительных его рассматриваются стандартные команды платформы для **New** и **откройте** элементам на **файл** меню.

##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Инициализация добавления пользователя к этим классам

Выше рисунках также предложить точек, в которых можно переопределить функции-члены для инициализации объектов приложения. Переопределение `OnInitialUpdate` в представлении класса — лучшее место для инициализации представления. `OnInitialUpdate` Вызов происходит сразу после создания окна фрейма и представлении в фрейме окна вложенный документ, его. Например, если представление является представлением прокрутки (производный от `CScrollView` вместо `CView`), следует задать размер представления, в зависимости от размера документа в вашей `OnInitialUpdate` переопределить. (Этот процесс описан в описании класса [CScrollView](../mfc/reference/cscrollview-class.md).) Можно переопределить `CDocument` функции-члены `OnNewDocument` и `OnOpenDocument` для предоставления конкретного приложения инициализации документа. Как правило оба необходимо переопределить, так как документ можно создать двумя способами.

В большинстве случаев переопределение должен вызывать версии базового класса. Дополнительные сведения см. в разделе функции-члены именованного классов [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), и [CWinApp](../mfc/reference/cwinapp-class.md) в MFC Справочник по библиотеке.

## <a name="see-also"></a>См. также

[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](../mfc/document-template-creation.md)<br/>
[Создание документа или представления](../mfc/document-view-creation.md)<br/>
[Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)

