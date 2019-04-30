---
title: Сопоставление сообщений Windows с классом
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 7e15f52e41d4ac91a839629342258128db86e2d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363860"
---
# <a name="mapping-windows-messages-to-your-class"></a>Сопоставление сообщений Windows с классом

Если вам нужна диалогового окна для обработки сообщений Windows, переопределяют функции соответствующий обработчик. Чтобы сделать это, используйте окно свойств для [сопоставление сообщений](../mfc/reference/mapping-messages-to-functions.md) в класс диалоговых окон. Это производит запись схемы сообщений для каждого сообщения и добавляет функции-члены обработчика сообщений для класса. Используйте редактор исходного кода Visual C++ для написания кода в обработчике сообщений.

Можно также переопределить функции-члены [CDialog](../mfc/reference/cdialog-class.md) и его базовых классов, особенно [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)

- [Часто переопределяемые функции-члены](../mfc/commonly-overridden-member-functions.md)

- [Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)
