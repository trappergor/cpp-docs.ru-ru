---
title: Изменение сетки макета | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
ms.assetid: ec31f595-7542-485b-806f-efbaeccc1b3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bafa66a382566ed096f70c752c461d8f3e2ca85
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010293"
---
# <a name="modifying-the-layout-grid"></a>Изменение сетки макета
При размещении или упорядочение элементов управления в диалоговом окне, можно использовать для более точного размещения сетки макета. Если сетка включена, чтобы «привязать» пунктирными линиями сетки как намагниченный отобразятся элементы управления. Можно включать эту функцию «прикрепить к сетке» и отключать и изменять размер ячеек сетки.  
  
### <a name="to-turn-the-layout-grid-on-or-off"></a>Чтобы выключать сетки макета  
  
1.  Из **формат** меню, выберите **параметры направляющих**.  
  
2.  В [диалоговое окно "Параметры направляющих"](../windows/guide-settings-dialog-box.md)установите или снимите **сетки** кнопки.  
  
     Можно управлять сетки в отдельных **диалоговое окно** окон редактора с помощью **сетка** , нажмите кнопку [редактор диалоговых окон инструментов](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
### <a name="to-change-the-size-of-the-layout-grid"></a>Чтобы изменить размер сетки макета  
  
1.  Из **формат** меню, выберите **параметры направляющих**.  
  
2.  В [диалоговое окно "Параметры направляющих"](../windows/guide-settings-dialog-box.md), введите высоту и ширину в единицах диалогового окна для ячеек в сетке. Минимальные значения высоты или ширины — 4 DLU. Дополнительные сведения о единицах диалогового окна см. в разделе [упорядочение элементов управления в диалоговых окнах](../windows/arrangement-of-controls-on-dialog-boxes.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)   
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)