---
title: Стили окна фрейма (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 102b3a4c8372a53aada23ad448ce5dc1cf323a97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343765"
---
# <a name="frame-window-styles-c"></a>Стили окна фрейма (C++)
Окна фрейма, можно получить с помощью платформы подходят для большинства программ, но можно получить дополнительную гибкость при помощи дополнительных функций [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) и глобальные функции MFC [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` функция-член из `CWnd`.  
  
 Если применить **WS_HSCROLL** и **WS_VSCROLL** стили основную область окна, вместо них применяются к **MDICLIENT** окна, поэтому можно прокручивать **MDICLIENT** области.  
  
 Если окно **FWS_ADDTOTITLE** (который по умолчанию он разрешен) установлен бит стиля, представление сообщает фрейм окна, задайте имя для отображения в заголовке окна на основе имени представления документа.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Управление дочерними окнами MDI (MDICLIENT)](../mfc/managing-mdi-child-windows.md), окна внутри фрейма MDI, содержащий дочерние окна MDI  
  
-   [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Стили окна](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>См. также  
 [Окна фрейма](../mfc/frame-windows.md)

