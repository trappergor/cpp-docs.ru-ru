---
title: Компоненты диалоговых окон в платформе
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: cf01e7b881b8f5c9c5ba9847ccf4e15dee3e18d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518590"
---
# <a name="dialog-box-components-in-the-framework"></a>Компоненты диалоговых окон в платформе

В платформе MFC диалоговое окно состоит из двух компонентов:

- Ресурс шаблона диалогового окна, который определяет элементы управления диалогового окна и их размещения.

   Ресурс диалогового окна сохраняет шаблон диалогового окна, из которого Windows создает диалоговое окно и отображает его. Шаблон указывает характеристики диалогового окна, включая его размер, расположение, стиль и типы и положение элементов управления диалогового окна. Обычно используется хранится в виде ресурса шаблона диалогового окна, но можно также создать собственный шаблон в памяти.

- Производный от класса диалогового окна, [CDialog](../mfc/reference/cdialog-class.md), которые обеспечивают программный интерфейс для управления в диалоговом окне.

   Диалоговое окно является окном и прикрепляется к окну Windows при отображении. При создании окна диалога ресурса шаблона диалогового окна используется в качестве шаблона для создания дочерних элементов управления окна для диалогового окна.

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

