---
title: Создание новых документов, окон и представлений
ms.date: 11/19/2018
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
ms.openlocfilehash: aa1c58b02df92d79ca9915032b97fb5c0e2eaffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371668"
---
# <a name="creating-new-documents-windows-and-views"></a>Создание новых документов, окон и представлений

Следующие цифры дают обзор процесса создания документов, представлений и окон кадра. Другие статьи, которые сосредоточены на участвующих объектов представить более подробную информацию.

По завершении этого процесса, сотрудничающие объекты существуют и хранят указатели друг к другу. Следующие цифры показывают последовательность, в которой создаются объекты. Вы можете следить за последовательностью от фигуры к фигуре.

![Последовательность создания документа](../mfc/media/vc387l1.gif "Последовательность создания документа") <br/>
Последовательность в создании документа

![Последовательность создания окна фрейма](../mfc/media/vc387l2.png "Последовательность создания окна фрейма") <br/>
Последовательность в создании окна рамы

![Последовательность создания представления](../mfc/media/vc387l3.gif "Последовательность создания представления") <br/>
Последовательность в создании представления

Для получения информации о том, как фреймворк инициализирует новый [CFrameWnd](../mfc/reference/cframewnd-class.md)документ, представление и объекты окна [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) кадра, см. [CDocument](../mfc/reference/cdocument-class.md) [CView](../mfc/reference/cview-class.md) [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) Также [см. Техническое примечание 22](../mfc/tn022-standard-commands-implementation.md), в котором далее объясняется процесс создания и инициализации при обсуждении стандартных команд платформы для **новых** и **открытых** элементов в меню **файла.**

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a>Инициализация собственных дополнений к этим классам

Предыдущие цифры также указывают на точки, в которых можно переопределить функции членов для инициализации объектов приложения. Переопределение `OnInitialUpdate` класса представления является лучшим местом для инициализации представления. Вызов `OnInitialUpdate` происходит сразу после создания окна кадра и прикрепляется к документу представление в окне кадра. Например, если представление прокрутки — `CScrollView` это `CView`представление прокрутки (полученное из `OnInitialUpdate` нее), следует установить размер представления на основе размера документа в переопределением. (Этот процесс описан в описании класса [CScrollView](../mfc/reference/cscrollview-class.md).) Вы можете переопределить `CDocument` `OnNewDocument` функции участника и `OnOpenDocument` предоставить инициализацию документа для конкретного приложения. Как правило, необходимо переопределить оба документа, поскольку документ может быть создан двумя способами.

В большинстве случаев переопределение должно вызывать версию базового класса. Для получения дополнительной информации смотрите названные функции членов классов [CDocument,](../mfc/reference/cdocument-class.md) [CView,](../mfc/reference/cview-class.md) [CFrameWnd](../mfc/reference/cframewnd-class.md)и [CWinApp](../mfc/reference/cwinapp-class.md) в справочнике библиотеки MFC.

## <a name="see-also"></a>См. также раздел

[Шаблоны документов и процесс создания документов/просмотра](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](../mfc/document-template-creation.md)<br/>
[Создание документов/просмотра](../mfc/document-view-creation.md)<br/>
[Отношения между объектами МФЦ](../mfc/relationships-among-mfc-objects.md)
