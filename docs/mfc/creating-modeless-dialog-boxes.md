---
title: Создание немодальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 71cca82e667ddbf5cfc4c2abb5880cd69c7fafae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388492"
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон

Для немодального диалогового окна необходимо предоставить собственный открытый конструктор в класс диалогового окна. Чтобы создать немодального диалогового окна, вызовите ваш открытый конструктор, а затем вызовите объекта диалогового окна [создать](../mfc/reference/cdialog-class.md#create) функция-член для загрузки ресурса диалогового окна. Можно вызвать **создать** во время или после вызова этого конструктора. Если ресурс диалогового окна со свойством **WS_VISIBLE**, немедленно появится диалоговое окно. Если нет, следует вызвать его [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) функция-член.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)
