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
ms.openlocfilehash: 649d64f8e8b894027b9d6850b62d357d79c1dafa
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616275"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Создание и отображение диалоговых окон

Создание объекта диалогового окна является двухфазной операцией. Сначала создайте объект диалогового окна, а затем — диалоговое окно. Модальные и немодальные диалоговые окна немного отличаются в процессе, который используется для их создания и вывода. В следующей таблице показано, как обычно создаются и отображаются модальные и немодальные диалоговые окна.

### <a name="dialog-creation"></a>Создание диалогового окна

|Тип диалога|Создание|
|-----------------|----------------------|
|[Модаль](creating-modeless-dialog-boxes.md)|Создайте `CDialog` , а затем вызовите `Create` функцию члена.|
|[Косы](creating-modal-dialog-boxes.md)|Создайте `CDialog` , а затем вызовите `DoModal` функцию члена.|

При необходимости можно создать диалоговое окно из созданного [шаблона диалогового окна в памяти](using-a-dialog-template-in-memory.md) , а не из ресурса шаблона диалогового окна. Однако это дополнительная тема.

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
