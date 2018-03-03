---
title: "Стили окна фрейма (C++) | Документы Microsoft"
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
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5bdc0204c538f476c791657d8b29a28b7baedd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-styles-c"></a>Стили окна фрейма (C++)
Окна фрейма, можно получить с помощью платформы подходят для большинства программ, но можно получить дополнительную гибкость при помощи дополнительных функций [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) и глобальные функции MFC [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow`функция-член из `CWnd`.  
  
 Если применить **WS_HSCROLL** и **WS_VSCROLL** стили основную область окна, вместо них применяются к **MDICLIENT** окна, поэтому можно прокручивать **MDICLIENT** области.  
  
 Если окно **FWS_ADDTOTITLE** (который по умолчанию он разрешен) установлен бит стиля, представление сообщает фрейм окна, задайте имя для отображения в заголовке окна на основе имени представления документа.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Управление дочерними окнами MDI (MDICLIENT)](../mfc/managing-mdi-child-windows.md), окна внутри фрейма MDI, содержащий дочерние окна MDI  
  
-   [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Стили окна](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>См. также  
 [Окна фрейма](../mfc/frame-windows.md)

