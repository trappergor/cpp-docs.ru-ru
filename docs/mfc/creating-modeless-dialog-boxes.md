---
title: Создание немодальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 4cc2bc0ce54ad658a8bf13e70a8fa54479cbbf79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453710"
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон

Для немодального диалогового окна необходимо предоставить собственный открытый конструктор в класс диалогового окна. Чтобы создать немодального диалогового окна, вызовите ваш открытый конструктор, а затем вызовите объекта диалогового окна [создать](../mfc/reference/cdialog-class.md#create) функция-член для загрузки ресурса диалогового окна. Можно вызвать **создать** во время или после вызова этого конструктора. Если ресурс диалогового окна со свойством **WS_VISIBLE**, немедленно появится диалоговое окно. Если нет, следует вызвать его [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) функция-член.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

