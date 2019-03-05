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
ms.openlocfilehash: 87b3405f1441e730cf5c9ce7fc03d2c7372e55db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289537"
---
# <a name="initializing-the-dialog-box"></a>Инициализация диалогового окна

После диалогового окна поле и все его элементы управления создаются, но только перед отображением диалогового окна поле (любого типа) на экране объекта диалогового окна [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызывается функция-член. Для модального диалогового окна, это происходит во время `DoModal` вызова. Для немодального диалогового окна `OnInitDialog` вызывается, когда `Create` вызывается. Обычно переопределяется `OnInitDialog` для инициализации элементов управления диалогового окна, такие как установка начальный текст из поля редактирования. Необходимо вызвать `OnInitDialog` функция-член базового класса, `CDialog`, из вашего `OnInitDialog` переопределить.

Если вы хотите задать цвет фона диалогового окна (и, все другие диалоговые окна в приложении), см. в разделе [Установка цвета фона диалогового окна](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)
