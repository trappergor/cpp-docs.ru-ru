---
title: Задание ширины горизонтальной полосы прокрутки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34545a01c01146992c7d88ecabec1a29a7b438f2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892801"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Задание ширины горизонтальной полосы прокрутки
При добавлении списка с горизонтальной полосы прокрутки в диалоговое окно, с помощью классов MFC, полосы прокрутки не появится автоматически в приложении.  
  
### <a name="to-make-the-scroll-bar-appear"></a>Чтобы сделать отображение полосы прокрутки  
  
1.  Установить максимальную ширину для самого широкого элемента путем вызова [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) в коде.  
  
     Без это значение не задано полоса прокрутки не появится, даже если элементы в списке шире поля.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 MFC  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)

