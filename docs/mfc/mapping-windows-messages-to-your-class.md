---
title: Сопоставление сообщений Windows с классом
ms.date: 09/06/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
- Class Wizard [MFC]
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 0f1207faca56acd709db86478722eba85eeb284a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685615"
---
# <a name="mapping-windows-messages-to-your-class"></a>Сопоставление сообщений Windows с классом

Если диалоговое окно требуется для обработки сообщений Windows, переопределите соответствующие функции обработчика. Для этого выберите вкладку **представление классов** в **Обозреватель решений**, щелкните правой кнопкой мыши класс, представляющий диалоговое окно, и выберите пункт [мастер классов](reference/mfc-class-wizard.md). С помощью мастера [сопоставьте сообщения](../mfc/reference/mapping-messages-to-functions.md) с классом диалогового окна. При этом записывается запись схемы сообщения для каждого сообщения и добавляются функции-члены обработчика сообщений в класс. Используйте редактор кода для написания кода в обработчиках сообщений.

Можно также переопределить функции элементов класса [CDialog](../mfc/reference/cdialog-class.md) и его базовых классов, особенно [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)

- [Часто переопределенные функции элементов](../mfc/commonly-overridden-member-functions.md)

- [Часто добавляемые функции элементов](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
