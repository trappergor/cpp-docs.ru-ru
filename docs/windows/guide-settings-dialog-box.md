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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 47bd233e384bbe21775d02b35cb878bf6bc402b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
## <a name="grid-spacing"></a>шаг сетки  
 Параметры направляющими в единицах диалогового (окна DLU).  
  
 **Ширина: DLU**  
  
 Задает ширину сетки макета в единицах диалогового окна. Горизонтальная Единица диалогового окна — Средняя Ширина шрифта диалогового деленная на четыре.  
  
 **Высота: DLU**  
  
 Задает высоту сетки макета в единицах диалогового окна. Вертикальная Единица диалогового окна — это средняя высота шрифта диалогового деленная на восемь.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Изменение сетки макета](../windows/modifying-the-layout-grid.md)   
 [Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)

