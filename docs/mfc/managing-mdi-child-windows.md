---
title: "Управление дочерними окнами MDI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MDICLIENT
dev_langs: C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ebcd6e484385ada3cd3d5ccfe450e7e25f539eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="managing-mdi-child-windows"></a>Управление дочерними окнами MDI
MDI-окна главного фрейма (по одному для каждого приложения) содержать специальный дочернего окна вызывается **MDICLIENT** окна. **MDICLIENT** окна управляет клиентской области фрейма главного окна, и в свою очередь есть дочерние окна: окон документов, производный от `CMDIChildWnd`. Так как окна документов фреймов сами (дочерние окна MDI), они также могут иметь свои собственные дочерние элементы. Во всех этих случаях родительское окно управляет его дочерних окон и пересылает некоторые команды к ним.  
  
 В окне фрейма MDI, управляет фрейм окна **MDICLIENT** окна, изменения положения его вместе с панели элементов управления. **MDICLIENT** окна, в свою очередь, управляет все рамки дочерних MDI-окон. На следующем рисунке показана связь между окне фрейма MDI, его **MDICLIENT** окна и его дочерних окон фрейма документа.  
  
 ![Дочерние окна в окне фрейма MDI](../mfc/media/vc37gb1.gif "vc37gb1")  
Окна фрейма MDI и дочерних элементов  
  
 При наличии окне фрейма MDI также работает в сочетании с текущее дочернее окно MDI. Окно области MDI делегирует сообщения команд дочернюю MDI-ФОРМУ перед повторной попыткой их обработки сам.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
-   [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

