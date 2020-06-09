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
ms.openlocfilehash: 7a714b5d7ba97c12b7134fa4890bddf5ed095c5b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620564"
---
# <a name="creating-new-documents-windows-and-views"></a>Создание новых документов, окон и представлений

На следующих рисунках представлен обзор процесса создания документов, представлений и окон фрейма. Другие статьи, в которых основное внимание уделяется участвующим объектам, содержат дополнительные сведения.

После завершения этого процесса существуют взаимодействующие объекты и они сохраняют указатели друг на друга. На следующих рисунках показана последовательность, в которой создаются объекты. Вы можете следовать последовательности, представленной на рисунке.

![Последовательность создания документа](../mfc/media/vc387l1.gif "Последовательность создания документа") <br/>
Последовательность в создании документа

![Последовательность создания окна фрейма](../mfc/media/vc387l2.png "Последовательность создания окна фрейма") <br/>
Последовательность при создании окна фрейма

![Последовательность создания представления](../mfc/media/vc387l3.gif "Последовательность создания представления") <br/>
Последовательность при создании представления

Сведения о том, как платформа инициализирует новый документ, представление и объекты окна кадров, см. в разделе Классы [CDocument](reference/cdocument-class.md), [CView](reference/cview-class.md), [CFrameWnd](reference/cframewnd-class.md), [CMDIFrameWnd](reference/cmdiframewnd-class.md)и [CMDIChildWnd](reference/cmdichildwnd-class.md) в справочнике по библиотеке MFC. См. также [техническое Примечание 22](tn022-standard-commands-implementation.md), в котором рассматриваются процессы создания и инициализации в соответствии с описанием стандартных команд платформы для **новых** и **открытых** элементов в меню **файл** .

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a>Инициализация собственных дополнений к этим классам

На предыдущих рисунках также предлагаются точки, в которых можно переопределить функции элементов для инициализации объектов приложения. Переопределение `OnInitialUpdate` в классе представления является лучшим местом для инициализации представления. `OnInitialUpdate`Вызов происходит сразу после создания фрейма окна, а представление в окне фрейма прикрепляется к его документу. Например, если представление является представлением с прокруткой (производным от `CScrollView` , а не `CView` ), следует задать размер представления в зависимости от размера документа в `OnInitialUpdate` переопределении. (Этот процесс описан в описании класса [кскроллвиев](reference/cscrollview-class.md).) Можно переопределить функции- `CDocument` члены `OnNewDocument` и `OnOpenDocument` обеспечить инициализацию документа для конкретного приложения. Как правило, необходимо переопределить оба способа, так как документ можно создать двумя способами.

В большинстве случаев переопределение должно вызывать версию базового класса. Дополнительные сведения см. в разделе функции именованных элементов классов [CDocument](reference/cdocument-class.md), [CView](reference/cview-class.md), [CFrameWnd](reference/cframewnd-class.md)и [CWinApp](reference/cwinapp-class.md) в справочнике по библиотеке MFC.

## <a name="see-also"></a>См. также раздел

[Шаблоны документов и процесс создания документа/представления](document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](document-template-creation.md)<br/>
[Создание документа или представления](document-view-creation.md)<br/>
[Связи между объектами MFC](relationships-among-mfc-objects.md)
