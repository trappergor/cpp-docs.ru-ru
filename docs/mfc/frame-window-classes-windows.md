---
title: Кадр классы окон (Windows) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43d6df0231f9d8d1d64d01bd12fa7209eb7b537d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345069"
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

