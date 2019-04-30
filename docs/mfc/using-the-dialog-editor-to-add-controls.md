---
title: Использование редактора диалоговых окон для добавления элементов управления
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controls [MFC], adding to dialog boxes
- Dialog editor, creating controls
- common controls [MFC], adding
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
ms.openlocfilehash: b88056d1c44e434e77f3f3b94976bf92516bbf3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411491"
---
# <a name="using-the-dialog-editor-to-add-controls"></a>Использование редактора диалоговых окон для добавления элементов управления

При создании ресурса шаблона диалогового окна с [редактор диалоговых окон](../windows/dialog-editor.md), перетащите элементы управления из палитры элементов управления и перетащить их в диалоговом окне. Это добавляет спецификации для данного типа элемента управления ресурса шаблона диалогового окна. При создании объекта диалогового окна и вызовите его `Create` или `DoModal` функция-член, платформа создает элемент управления Windows и помещает его в диалоговом окне на экране.

Вы можете вместо этого [вручную создавать элементы управления](../mfc/adding-controls-by-hand.md) Если требуется. Это больше работы.

## <a name="see-also"></a>См. также

[Создание и использование элементов управления](../mfc/making-and-using-controls.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
