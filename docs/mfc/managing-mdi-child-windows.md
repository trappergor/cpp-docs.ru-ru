---
title: Управление дочерними окнами MDI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58ddef11e56da760bbecaa47f03dfa6c57dfa3ed
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929485"
---
# <a name="managing-mdi-child-windows"></a>Управление дочерними окнами MDI
MDI-окна главного фрейма (по одному для каждого приложения) содержать специальный дочернее окно, окно MDICLIENT вызывается. Окно MDICLIENT управляет клиентской области фрейма главного окна, и в свою очередь есть дочерние окна: окон документов, производный от `CMDIChildWnd`. Так как окна документов фреймов сами (дочерние окна MDI), они также могут иметь свои собственные дочерние элементы. Во всех этих случаях родительское окно управляет его дочерних окон и пересылает некоторые команды к ним.  
  
 В окне фрейма MDI окно фрейма управляет MDICLIENT-окно, изменить его расположение в сочетании с панели элементов управления. MDICLIENT-окно, в свою очередь, управляет все рамки дочерних MDI-окон. На следующем рисунке показана связь между окне фрейма MDI, его окно MDICLIENT и его дочерних окон фрейма документа.  
  
 ![Дочерние окна в окне фрейма MDI](../mfc/media/vc37gb1.gif "vc37gb1")  
Окна фрейма MDI и дочерних элементов  
  
 При наличии окне фрейма MDI также работает в сочетании с текущее дочернее окно MDI. Окно области MDI делегирует сообщения команд дочернюю MDI-ФОРМУ перед повторной попыткой их обработки сам.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)  
  
-   [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

