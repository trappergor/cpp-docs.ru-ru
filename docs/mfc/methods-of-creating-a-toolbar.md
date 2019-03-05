---
title: Способы создания панели инструментов
ms.date: 11/04/2016
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
ms.openlocfilehash: f269ad990042f51554ec598b0bddbe5a6d7776b8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304396"
---
# <a name="methods-of-creating-a-toolbar"></a>Способы создания панели инструментов

MFC предоставляет два класса для создания панели инструментов. [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (который создает оболочку для общего элемента управления Windows API). `CToolBar` предоставляет все функциональные возможности стандартного элемента панели инструментов управления и обрабатывает многие необходимые общие параметры управления и структуры. Тем не менее, полученный исполняемый файл обычно будет больше, созданные с помощью `CToolBarCtrl`.

`CToolBarCtrl` Обычно результаты в исполняемый файл меньшего размера, а также может предпочесть использование `CToolBarCtrl` Если вы не собираетесь интегрировать панели инструментов в архитектуру MFC. Если вы планируете использовать `CToolBarCtrl` и интегрировать в архитектуру MFC панели инструментов, необходимо выполнить дополнительные действия для обмена данными инструментов управления манипуляций с MFC. Это взаимодействие несложно; Тем не менее, это дополнительную работу, ненужные при использовании `CToolBar`.

Visual C++ предоставляет два способа для использования стандартного элемента управления панели инструментов.

- Создайте панель инструментов с помощью `CToolBar`, а затем вызвать [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) для получения доступа к `CToolBarCtrl` функций-членов.

- Создайте панель инструментов с помощью [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)в конструктор.

Каждый из этих методов будет предоставить вам доступ к функции-члены элемента управления панели инструментов. При вызове `CToolBar::GetToolBarCtrl`, он возвращает ссылку на `CToolBarCtrl` объекта, поэтому вы можете использовать любой набор функций-членов. См. в разделе [CToolBar](../mfc/reference/ctoolbar-class.md) сведения о построении и создания панели инструментов с помощью `CToolBar`.

## <a name="see-also"></a>См. также

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
