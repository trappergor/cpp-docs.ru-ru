---
title: Сопоставление сообщений Windows с классом | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e5c51cfccfa360b7f677ca3a30b7a05e0d4a799
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374468"
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

