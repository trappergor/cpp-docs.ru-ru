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
ms.openlocfilehash: 6d23e4d2c9249ce248eb8092963036f2ba5cacac
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685745"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Создание и отображение диалоговых окон

Создание объекта диалогового окна является двухфазной операцией. Сначала создайте объект диалогового окна, а затем — диалоговое окно. Модальные и немодальные диалоговые окна немного отличаются в процессе, который используется для их создания и вывода. В следующей таблице показано, как обычно создаются и отображаются модальные и немодальные диалоговые окна.

### <a name="dialog-creation"></a>Создание диалогового окна

|Тип диалогового окна|Создание|
|-----------------|----------------------|
|[Модаль](../mfc/creating-modeless-dialog-boxes.md)|Создайте `CDialog`, а затем вызовите функцию `Create` члена.|
|[Косы](../mfc/creating-modal-dialog-boxes.md)|Создайте `CDialog`, а затем вызовите функцию `DoModal` члена.|

При необходимости можно создать диалоговое окно из созданного [шаблона диалогового окна в памяти](../mfc/using-a-dialog-template-in-memory.md) , а не из ресурса шаблона диалогового окна. Однако это дополнительная тема.

## <a name="see-also"></a>См. также:

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
