---
title: "Стили полосы прокрутки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SBS_VERT"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN"
  - "SBS_LEFTALIGN"
  - "SBS_RIGHTALIGN"
  - "SBS_TOPALIGN"
  - "SBS_SIZEBOXTOPLEFTALIGN"
  - "SBS_BOTTOMALIGN"
  - "SBS_SIZEBOX"
  - "SBS_HORZ"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBS_BOTTOMALIGN - константа"
  - "SBS_HORZ - константа"
  - "SBS_LEFTALIGN - константа"
  - "SBS_RIGHTALIGN - константа"
  - "SBS_SIZEBOX - константа"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN - константа"
  - "SBS_SIZEBOXTOPLEFTALIGN - константа"
  - "SBS_TOPALIGN - константа"
  - "SBS_VERT - константа"
  - "полосы прокрутки, стили"
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Стили полосы прокрутки
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SBS\_BOTTOMALIGN**, **SBS\_HORZ** со стилем.  Нижний край полосы прокрутки выравнивается с нижний край прямоугольника, определенного в функции\-члене **Создать**.  "Полоса прокрутки" имеет высоту по умолчанию для отображения полос прокрутки системы.  
  
-   **SBS\_HORZ** указывает горизонтальной полосы прокрутки.  Если ни стиль **SBS\_BOTTOMALIGN** и **SBS\_TOPALIGN** определен, полоса прокрутки имеет высоту, ширину и уступанную положение функцию\-член **Создать**.  
  
-   **SBS\_LEFTALIGN**, **SBS\_VERT** со стилем.  Левый край полосы прокрутки выравнивается с левый край прямоугольника, определенного в функции\-члене **Создать**.  "Полоса прокрутки" имеет ширину по умолчанию для отображения полос прокрутки системы.  
  
-   **SBS\_RIGHTALIGN**, **SBS\_VERT** со стилем.  Правый край полосы прокрутки выравнивается с правым краем прямоугольника, определенного в функции\-члене **Создать**.  "Полоса прокрутки" имеет ширину по умолчанию для отображения полос прокрутки системы.  
  
-   **SBS\_SIZEBOX** указывает размер окна.  Если ни стиль **SBS\_SIZEBOXBOTTOMRIGHTALIGN** и **SBS\_SIZEBOXTOPLEFTALIGN** определен, то окно размера имеет высоту, ширину и уступанную положение функцию\-член **Создать**.  
  
-   **SBS\_SIZEBOXBOTTOMRIGHTALIGN**, **SBS\_SIZEBOX** со стилем.  В нижнем правом углу окна размера выравнивается с нижним углом прямоугольника, определенного в функции\-члене **Создать**.  Окно размера имеет размер по умолчанию для окон размера системы.  
  
-   **SBS\_SIZEBOXTOPLEFTALIGN**, **SBS\_SIZEBOX** со стилем.  Верхний левый угол окна размера выравнивается с верхний левый угол которого расположен прямоугольника, определенного в функции\-члене **Создать**.  Окно размера имеет размер по умолчанию для окон размера системы.  
  
-   **SBS\_SIZEGRIP** так же, как **SBS\_SIZEBOX**, но с созданным краем.  
  
-   **SBS\_TOPALIGN**, **SBS\_HORZ** со стилем.  Верхний край полосы прокрутки выравнивается с верхний край прямоугольника, определенного в функции\-члене **Создать**.  "Полоса прокрутки" имеет высоту по умолчанию для отображения полос прокрутки системы.  
  
-   **SBS\_VERT** указывает вертикальную полосу прокрутки.  Если ни стиль **SBS\_RIGHTALIGN** и **SBS\_LEFTALIGN** определен, полоса прокрутки имеет высоту, ширину и уступанную положение функцию\-член **Создать**.  
  
## См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../Topic/CScrollBar::Create.md)   
 [Scroll Bar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb787533)