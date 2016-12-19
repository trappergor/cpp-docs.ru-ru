---
title: "Использование необрезанного контекста устройства | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX - элементы управления, необрезанное содержимое устройства"
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование необрезанного контекста устройства
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если точно известно, что элемент управления не запрашивает вне прямоугольника клиента можно осуществляет небольшой, но обнаруженное увеличение скорости путем отключения в `IntersectClipRect`, сделанный `COleControl`.  Для этого следует удалить флажок **clipPaintDC** из набора флажков, возвращенных методом [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Примеры.  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/CPP/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/using-an-unclipped-device-context_3.cpp)]  
  
 Код, чтобы удалить этот флажок создается автоматически, если выбирать параметр **Необрезанное содержимое устройства** на странице [Параметры элементов управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md), создать элемент управления с помощью мастера элементов управления ActiveX MFC.  
  
 При использовании безоконную активацию, эта оптимизация не влияет.  
  
## См. также  
 [Элементы управления ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)