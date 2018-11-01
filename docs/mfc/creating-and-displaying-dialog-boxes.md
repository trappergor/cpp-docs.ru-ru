---
title: Создание и отображение диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: 778ee0cbb154c65b0cc74a207a175354c2e2a90b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431087"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Создание и отображение диалоговых окон

Создание объекта диалогового окна является двухэтапную операцию. Во-первых создайте объект диалогового окна, а затем создать диалоговое окно. Модальные и немодальные диалоговые окна отличаются разбираются в процесс, используемый для создания и отображения их. В следующей таблице перечислены диалоговое окно как модальные и немодальные поля являются обычно создается и отображается.

### <a name="dialog-creation"></a>Создание диалогового окна

|Тип диалогового окна|Как создать его|
|-----------------|----------------------|
|[Немодальное окна](../mfc/creating-modeless-dialog-boxes.md)|Создать `CDialog`, затем вызовите `Create` функция-член.|
|[Модальное](../mfc/creating-modal-dialog-boxes.md)|Создать `CDialog`, затем вызовите `DoModal` функция-член.|

Можно Если вы хотите создать диалоговое окно, в [шаблона диалогового окна в памяти](../mfc/using-a-dialog-template-in-memory.md) , сформированного, а не из ресурса шаблона диалогового окна. Это довольно сложная тема, тем не менее.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

