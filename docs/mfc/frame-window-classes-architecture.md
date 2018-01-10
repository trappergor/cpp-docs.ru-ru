---
title: "Фрейма окна классов (архитектура) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.frame
dev_langs: C++
helpviewer_keywords: frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1caf8e4b93e18675b810ced962df6e8adcf521a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

