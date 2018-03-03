---
title: "Компоненты диалоговых окон в платформе | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840e66def6a908b26b5021537eddee68c50a9628
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-box-components-in-the-framework"></a>Компоненты диалоговых окон в платформе
Диалоговое окно в платформы MFC состоит из двух компонентов:  
  
-   Ресурс шаблона диалогового окна, который указывает поле диалогового окна элементы управления и их размещение.  
  
     Ресурс диалогового окна хранит шаблон диалогового окна, из которого Windows создает диалоговое окно и отображает его. Шаблон задает характеристики диалоговое окно «», включая его размер, расположение, стиль и типы и положение элементов управления в диалоговое окно «». Обычно используется хранится в виде ресурса шаблона диалогового окна, но можно также создать собственный шаблон в памяти.  
  
-   Диалоговый класс, производный от [CDialog](../mfc/reference/cdialog-class.md), которые обеспечивают программный интерфейс для управления диалоговым окном.  
  
     Диалоговое окно — это окно и будет присоединена к окну Windows при отображении. При создании диалоговом окне ресурса шаблона диалогового окна используется как шаблон для создания дочерних элементов управления окна для диалогового окна.  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

