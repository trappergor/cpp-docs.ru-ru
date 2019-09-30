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
ms.openlocfilehash: 15d01924be811a9c9ec8ea333870f444bf9aa61a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685834"
---
# <a name="dialog-box-components-in-the-framework"></a>Компоненты диалоговых окон в платформе

В платформе MFC диалоговое окно содержит два компонента:

- Ресурс диалогового шаблона, указывающий элементы управления диалогового окна и их размещение.

   В ресурсе диалогового окна сохраняется шаблон диалогового окна, из которого Windows создает диалоговое окно и отображает его. Шаблон определяет характеристики диалогового окна, включая его размер, расположение, стиль, а также типы и положения элементов управления диалогового окна. Обычно используется шаблон диалогового окна, хранящийся в качестве ресурса, но можно также создать собственный шаблон в памяти.

- Класс диалогового окна, производного от класса [CDialog](../mfc/reference/cdialog-class.md), для предоставления программного интерфейса для управления диалоговым окном.

   Диалоговое окно является окном и будет присоединено к окну Windows, когда оно видимо. При создании диалогового окна ресурс диалога-шаблона используется в качестве шаблона для создания дочерних элементов управления окна для диалогового окна.

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
