---
title: Сочетания клавиш для определенного потока | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e54fbb2709f5f5bb6d01c279cb369b91dbfcaed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372166"
---
# <a name="thread-specific-hot-keys"></a>Сочетания клавиш для определенного потока

Приложение задает сочетания клавиш определенного потока ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) с помощью Windows `RegisterHotKey` функции. Когда пользователь нажимает клавишу конкретного потока, Windows отправляет [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey) сообщение в начале очереди сообщений в определенном потоке. Сообщение WM_HOTKEY содержит виртуального кода клавиши, состояние сдвига и определяемые пользователем идентификатор конкретного сочетания клавиш, которая была нажата. Список стандартных коды виртуальных клавиш см. в разделе Winuser.h. Дополнительные сведения об этом методе см. в разделе [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).

Обратите внимание, что состояние сдвига помечает используемые в вызове `RegisterHotKey` не совпадают, возвращаемыми [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) функция-член; вам придется преобразовать эти флаги перед вызовом `RegisterHotKey`.

## <a name="see-also"></a>См. также

[Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

