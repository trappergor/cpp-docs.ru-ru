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
ms.openlocfilehash: 14cdf94bef79f254b4aaa2c1c0dfba6c88b7498b
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685629"
---
# <a name="initializing-the-dialog-box"></a>Инициализация диалогового окна

После создания диалогового окна и всех его элементов управления, но непосредственно перед тем, как на экране появится диалоговое окно (любого из типов), вызывается функция-член [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog) объекта диалогового окна. Для модального диалогового окна это происходит во время вызова `DoModal`. Для немодального диалогового окна `OnInitDialog` вызывается при вызове `Create`. Как правило, `OnInitDialog` переопределяются для инициализации элементов управления диалогового окна, например для установки исходного текста поля ввода. Необходимо вызвать функцию-член @no__t базового класса `CDialog` из переопределения `OnInitDialog`.

Если вы хотите задать цвет фона диалогового окна (и всех остальных диалоговых окон приложения), см. раздел [Настройка цвета фона диалогового окна](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>См. также

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
