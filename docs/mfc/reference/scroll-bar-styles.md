---
title: "Стили полосы прокрутки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SBS_VERT
- SBS_SIZEBOXBOTTOMRIGHTALIGN
- SBS_LEFTALIGN
- SBS_RIGHTALIGN
- SBS_TOPALIGN
- SBS_SIZEBOXTOPLEFTALIGN
- SBS_BOTTOMALIGN
- SBS_SIZEBOX
- SBS_HORZ
dev_langs:
- C++
helpviewer_keywords:
- SBS_HORZ constant
- SBS_TOPALIGN constant
- SBS_SIZEBOX constant
- SBS_BOTTOMALIGN constant
- SBS_VERT constant
- SBS_LEFTALIGN constant
- SBS_SIZEBOXBOTTOMRIGHTALIGN constant
- scroll bars, styles
- SBS_SIZEBOXTOPLEFTALIGN constant
- SBS_RIGHTALIGN constant
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 778fe7b0f6f6319884df4ed9c5ccbe8e34bd8d42
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="scroll-bar-styles"></a>Стили полосы прокрутки
-   **SBS_BOTTOMALIGN** с **SBS_HORZ** стиль. Нижний край полоса прокрутки выравнивается нижний край прямоугольника, заданного в **создать** функции-члена. Полоса прокрутки имеет высоту по умолчанию для системы полосы прокрутки.  
  
-   **SBS_HORZ** обозначает горизонтальной полосы прокрутки. Если ни одна из **SBS_BOTTOMALIGN** , ни **SBS_TOPALIGN** указанный стиль, полоса прокрутки имеет высоту, ширину и положение в **создать** функции-члена.  
  
-   **SBS_LEFTALIGN** с **SBS_VERT** стиль. В левой части полосы прокрутки выравнивается с левым краем прямоугольник, задаваемый в **создать** функции-члена. Полоса прокрутки имеет ширину по умолчанию для системы полосы прокрутки.  
  
-   **SBS_RIGHTALIGN** с **SBS_VERT** стиль. Правый край полосы прокрутки выравнивается с правого края прямоугольника, заданного в **создать** функции-члена. Полоса прокрутки имеет ширину по умолчанию для системы полосы прокрутки.  
  
-   **SBS_SIZEBOX** обозначает поле размер. Если ни одна из **SBS_SIZEBOXBOTTOMRIGHTALIGN** , ни **SBS_SIZEBOXTOPLEFTALIGN** указанный стиль, поле «размер» имеет высоту, ширину и положение в **создать** функции-члена.  
  
-   **SBS_SIZEBOXBOTTOMRIGHTALIGN** с **SBS_SIZEBOX** стиль. В правом нижнем углу поле размер выравнивается в правом нижнем углу прямоугольник, задаваемый в **создать** функции-члена. Поле «размер» имеет размер по умолчанию для системы размер поля.  
  
-   **SBS_SIZEBOXTOPLEFTALIGN** с **SBS_SIZEBOX** стиль. В верхний левый угол поле размер выравнивается с верхнего левого угла прямоугольника, заданного в **создать** функции-члена. Поле «размер» имеет размер по умолчанию для системы размер поля.  
  
-   **SBS_SIZEGRIP** как **SBS_SIZEBOX**, но вызванного границу.  
  
-   **SBS_TOPALIGN** с **SBS_HORZ** стиль. Верхний край полосы прокрутки выравнивается с верхним краем прямоугольник, задаваемый в **создать** функции-члена. Полоса прокрутки имеет высоту по умолчанию для системы полосы прокрутки.  
  
-   **SBS_VERT** обозначает вертикальной полосы прокрутки. Если ни одна из **SBS_RIGHTALIGN** , ни **SBS_LEFTALIGN** указанный стиль, полоса прокрутки имеет высоту, ширину и положение в **создать** функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create)   
 [Стили элемента управления полосы прокрутки](http://msdn.microsoft.com/library/windows/desktop/bb787533)


