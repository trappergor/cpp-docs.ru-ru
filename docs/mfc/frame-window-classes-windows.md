---
title: "Кадр классы окон (Windows) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2668a8334192d4de199f1c42a648b74add1ca5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-windows"></a>Классы окна фрейма (Windows)
Окна фрейма — это окна, которые фрейма приложения или части приложения. Окна фрейма обычно содержат другие окна, такие как представления, панели инструментов и строки состояния. В случае использования `CMDIFrameWnd`, они могут содержать `CMDIChildWnd` косвенно объектов.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Базовый класс для приложения SDI фрейма главного окна. Кроме того базовый класс для всех других классы окна фрейма.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Базовый класс для окна главного фрейма MDI-приложения.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Базовый класс для окна фрейма документа MDI-приложения.  
  
 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)  
 Окно фрейма половинной высоты, обычно отображается на плавающих панелях инструментов.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Предоставляет окна фрейма для представления, когда серверный документ изменяется на месте.  
  
## <a name="related-class"></a>Связанный класс  
 Класс `CMenu` предоставляет интерфейс, по которому необходимо получить доступ к меню приложения. Это полезно для динамически Управление меню во время выполнения. Например, при добавлении или удалении элементов меню в зависимости от контекста. Несмотря на то, что меню чаще всего используются с фреймов, можно также использовать с диалоговыми окнами и другими окнами nonchild.  
  
 [CMenu](../mfc/reference/cmenu-class.md)  
 Инкапсулирует `HMENU` дескриптор меню и контекстные меню приложения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

