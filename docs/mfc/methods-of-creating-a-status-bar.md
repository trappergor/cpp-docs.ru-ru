---
title: Способы создания строки состояния
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: a2301301d0012bd93ffedd0452dec140174402e0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276888"
---
# <a name="methods-of-creating-a-status-bar"></a>Способы создания строки состояния

MFC предоставляет два класса для создания строки состояния. [CStatusBar](../mfc/reference/cstatusbar-class.md) и [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (который создает оболочку для общего элемента управления Windows API). `CStatusBar` предоставляет все функциональные возможности строки общего элемента управления состояния, он автоматически взаимодействует с меню и панелей инструментов и обрабатывает многие необходимые общие параметры управления и структуры. Тем не менее, полученный исполняемый файл обычно будет больше, созданные с помощью `CStatusBarCtrl`.

`CStatusBarCtrl` Обычно результаты в исполняемый файл меньшего размера, а также может предпочесть использование `CStatusBarCtrl` Если вы не собираетесь интегрировать в строке состояния в MFC архитектуру. Если вы планируете использовать `CStatusBarCtrl` и интегрировать в строке состояния в MFC архитектуру, необходимо выполнить дополнительные действия для обмена данными управления манипуляций с MFC в строке состояния. Это взаимодействие несложно; Тем не менее, это дополнительную работу, ненужные при использовании `CStatusBar`.

Visual C++ предоставляет два способа, чтобы воспользоваться преимуществами общие строки состояния.

- Создание строки с помощью состояния `CStatusBar`, а затем вызвать [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) для получения доступа к `CStatusBarCtrl` функций-членов.

- Создание строки с помощью состояния [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)в конструктор.

Каждый из этих методов будет предоставить вам доступ к функции-члены элемента управления строкой состояния. При вызове `CStatusBar::GetStatusBarCtrl`, он возвращает ссылку на `CStatusBarCtrl` объекта, поэтому вы можете использовать любой набор функций-членов. См. в разделе [CStatusBar](../mfc/reference/cstatusbar-class.md) сведения о построении и создания индикатора с помощью `CStatusBar`.

## <a name="see-also"></a>См. также

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
