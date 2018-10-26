---
title: Компоненты диалоговых окон в платформе | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6936a48d1a3e1845d56c73524c84800d9d605155
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065516"
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

