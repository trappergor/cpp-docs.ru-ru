---
title: Инициализация диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 2312a158835b28e7a17a6c30bb1fa148a63c07fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507975"
---
# <a name="initializing-the-dialog-box"></a>Инициализация диалогового окна

После диалогового окна поле и все его элементы управления создаются, но только перед отображением диалогового окна поле (любого типа) на экране объекта диалогового окна [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызывается функция-член. Для модального диалогового окна, это происходит во время `DoModal` вызова. Для немодального диалогового окна `OnInitDialog` вызывается, когда `Create` вызывается. Обычно переопределяется `OnInitDialog` для инициализации элементов управления диалогового окна, такие как установка начальный текст из поля редактирования. Необходимо вызвать `OnInitDialog` функция-член базового класса, `CDialog`, из вашего `OnInitDialog` переопределить.

Если вы хотите задать цвет фона диалогового окна (и, все другие диалоговые окна в приложении), см. в разделе [Установка цвета фона диалогового окна](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

