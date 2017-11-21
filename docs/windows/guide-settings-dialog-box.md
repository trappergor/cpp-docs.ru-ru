---
title: "Руководство по диалоговое окно «Параметры» | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLUs (dialog units)
- Dialog editor, snap to guides
- grid spacing
- guides, settings
- dialog units (DLUs)
- layout grid in Dialog Editor
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
ms.assetid: 55381e1c-146a-4fa7-b1b3-b1492817615f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3389a92be2dcb1a183cfbc297e45fb8360a9288d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="guide-settings-dialog-box"></a>Диалоговое окно "Параметры направляющих"
## <a name="layout-guides"></a>Направляющие  
 Отображает параметры для направляющих макета.  
  
 **None**  
  
 Скрывает макета.  
  
 **Линейки и направляющие**  
  
 При включении добавляет линейку макета; руководства по может быть помещен в линейки. Направляющие по умолчанию – это поля, которые можно переместить путем перетаскивания. Щелкните в области линейки, чтобы разместить направляющую. Элементы управления «привязки» к направляющим при перемещении элементов управления или накладываются на них. Элементы управления также перемещаются вместе с руководством, присоединенная к нему. При присоединении элемента управления к направляющей с каждой стороны, и направляющая перемещается, размер.  
  
 **Сетка**  
  
 Создание сетки макета. Новые элементы управления автоматически будут привязаны к сетке.  
  
## <a name="grid-spacing"></a>Шаг сетки  
 Параметры направляющими в единицах диалогового (окна DLU).  
  
 **Ширина: DLU**  
  
 Задает ширину сетки макета в единицах диалогового окна. Горизонтальная Единица диалогового окна — Средняя Ширина шрифта диалогового деленная на четыре.  
  
 **Высота: DLU**  
  
 Задает высоту сетки макета в единицах диалогового окна. Вертикальная Единица диалогового окна — это средняя высота шрифта диалогового деленная на восемь.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Изменение сетки макета](../windows/modifying-the-layout-grid.md)   
 [Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)

