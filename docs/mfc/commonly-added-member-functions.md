---
title: Часто добавляемые функции-члены | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- MFC dialog boxes [MFC], control-notification messages
- dialog classes [MFC], commonly added member functions
ms.assetid: f6bd50e8-872a-4039-9996-a85bfccea18d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a07c034a15cd0b575dab4cb3b647e64e6ad16c7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428572"
---
# <a name="commonly-added-member-functions"></a>Часто добавляемые функции-члены

Если диалоговое окно содержит кнопок, отличный от ОК "или" Отмена ", необходимо написать обработчик сообщений функции-члены в класс диалогового окна реагировать на сообщения уведомление элемента управления, которые они создают. Например, см. в разделе [Scribble](../visual-cpp-samples.md) пример программы. Можно также обработать уведомление элемента управления сообщения от других элементов управления диалогового окна.

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Часто переопределяемые функции-члены](../mfc/commonly-overridden-member-functions.md)
