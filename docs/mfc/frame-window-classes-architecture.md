---
title: Фрейма окна классов (архитектура) | Документы Microsoft
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
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7de72b77be9be90ca876cfef943500a0312d183
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-classes-architecture"></a>Классы окна фрейма (архитектура)
В архитектуре "документ представление" окна фрейма, windows, которые содержат окно представления. Они также поддерживают необходимости управления полосы, присоединенными к ним.  
  
 В нескольких приложениях интерфейса (MDI) документа, главное окно является производным от `CMDIFrameWnd`. Ее косвенно содержит кадры документов, которые являются `CMDIChildWnd` объектов. `CMDIChildWnd` Объекты, в свою очередь, содержат представления документов.  
  
 В приложениях однооконный интерфейс (SDI), главного окна, производный от `CFrameWnd`, содержащей представление текущего документа.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Базовый класс для приложения SDI фрейма главного окна. Кроме того базовый класс для всех других классы окна фрейма.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Базовый класс для окна главного фрейма MDI-приложения.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Базовый класс для окна фрейма документа MDI-приложения.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Предоставляет окна фрейма для представления, когда серверный документ изменяется на месте.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

