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
ms.openlocfilehash: e0b7ff31576b345ac2911e62a6e10469845eecba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175034"
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
