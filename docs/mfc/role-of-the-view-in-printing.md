---
title: Роль просмотра при печати | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], printing
- OnDraw method [MFC], and printing
- printing [MFC], OnDraw method [MFC]
- printing [MFC], views
- CView class [MFC], role in printing
- printing views [MFC]
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c78756ea84df66b77f71d8f8ad8d0b9dfa1a6c9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377530"
---
# <a name="role-of-the-view-in-printing"></a>Роль просмотра при печати

Представление также играет два важных ролей в печать его связанный документ.

Представление:

- Использует тот же [OnDraw](../mfc/reference/cview-class.md#ondraw) код для рисования на принтере для рисования на экране.

- Управляет разделение на страницы для печати документа.

Дополнительные сведения о печати и о роли представления при печати, см. в разделе [печать и предварительный просмотр печати](../mfc/printing-and-print-preview.md).

## <a name="see-also"></a>См. также

[Использование представлений](../mfc/using-views.md)

