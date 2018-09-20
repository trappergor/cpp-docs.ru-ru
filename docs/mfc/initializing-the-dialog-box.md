---
title: Инициализация диалогового окна | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42526eea184cb4f28d5214fe0c56281ac6da9d6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426111"
---
# <a name="initializing-the-dialog-box"></a>Инициализация диалогового окна

После диалогового окна поле и все его элементы управления создаются, но только перед отображением диалогового окна поле (любого типа) на экране объекта диалогового окна [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызывается функция-член. Для модального диалогового окна, это происходит во время `DoModal` вызова. Для немодального диалогового окна `OnInitDialog` вызывается, когда `Create` вызывается. Обычно переопределяется `OnInitDialog` для инициализации элементов управления диалогового окна, такие как установка начальный текст из поля редактирования. Необходимо вызвать `OnInitDialog` функция-член базового класса, `CDialog`, из вашего `OnInitDialog` переопределить.

Если вы хотите задать цвет фона диалогового окна (и, все другие диалоговые окна в приложении), см. в разделе [Установка цвета фона диалогового окна](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

