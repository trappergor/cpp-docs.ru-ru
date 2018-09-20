---
title: Использование CHotKeyCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CHotKeyCtrl
dev_langs:
- C++
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd966b74590d0e7641f2f789b5c45f901a3cf8c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421509"
---
# <a name="using-chotkeyctrl"></a>Использование CHotKeyCtrl

"Горячий" ключа элемента управления, представленный классом [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), — это окно, отображающее текстовое представление сочетание клавиш, которые пользователь вводит в него, например CTRL + SHIFT + Q. Кроме того, обеспечена во внутреннее представление этот ключ в виде виртуального кода клавиши и набор флагов, которые представляют состояние сдвига. "Горячий" ключа элемента управления не задает сочетания клавиш — это зависит от вашей программы. (Список стандартные коды виртуальных клавиш, см. в разделе Winuser.h.)

Используйте "Горячий" ключей управления для получения ввода пользователя для какие сочетания клавиш, связываемое с окном или поток. "Горячий" Основные элементы управления часто используются в диалоговых окнах, такие, как может отображаться вместе с запросом пользователя, чтобы назначить сочетания клавиш. Отвечает за программы для получения значения, описывающие сочетания клавиш из "Горячий" ключа элемента управления и для вызова соответствующих функций должен быть сопоставлен клавиш окно или поток.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Использование элемента управления "Сочетание клавиш"](../mfc/using-a-hot-key-control.md)

- [Задание сочетания клавиш](../mfc/setting-a-hot-key.md)

- [Глобальные сочетания клавиш](../mfc/global-hot-keys.md)

- [Сочетания клавиш для определенного потока](../mfc/thread-specific-hot-keys.md)

## <a name="see-also"></a>См. также

[Элементы управления](../mfc/controls-mfc.md)

