---
title: "Выбор графического объекта в контексте устройства | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "контексты устройств, графические объекты"
  - "контексты устройств, выбор графических объектов в"
  - "объекты GDI [C++], контексты устройств"
  - "графические объекты, выбор в контексте устройств"
  - "время существования, графические объекты"
  - "SelectObject - метод"
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Выбор графического объекта в контексте устройства
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот раздел применим к использованию графических объектов в контексте устройства окна.  После [создание графического объекта](../mfc/one-stage-and-two-stage-construction-of-objects.md) необходимо выбрать в контексте устройства вместо объекта по умолчанию, хранящимися:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/CPP/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## Время существования графических объектов  
 Графический объект, возвращаемый [SelectObject](../Topic/CDC::SelectObject.md) является временным «.» Иными словами, он будет удален функцией\-членом класса [OnIdle](../Topic/CWinApp::OnIdle.md)`CWinApp` при следующем запуске программы получает время бездействия.  Если используется объект, возвращаемый `SelectObject` в одной функции без возврата элемента управления в главный цикл обработки сообщений, не будет иметь никакой проблемы.  
  
### Дополнительные сведения  
  
-   [Графические объекты](../mfc/graphic-objects.md)  
  
-   [От этап построения и двухшаговое графических объектов](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Контексты устройств](../Topic/Device%20Contexts.md)  
  
-   [Рисование в представлении](../mfc/drawing-in-a-view.md)  
  
## См. также  
 [Графические объекты](../mfc/graphic-objects.md)