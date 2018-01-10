---
title: "Работа с цветом (редактор изображений для значков) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.image.color
dev_langs: C++
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors, Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ad0c7df6804667c3bd243668193283ecee61c8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-color-image-editor-for-icons"></a>Работа с цветом (редактор изображений для значков)
Редактор изображений содержит множество функций, в частности, обработки и настроить цвета. Можно задать цвет переднего плана и фона, заливка цветом выделенной области или выберите цвет для образа для использования в качестве текущего цвета переднего плана и фона. Можно использовать средства на [панель инструментов редактора изображений](../windows/toolbar-image-editor-for-icons.md) вместе с палитра цветов в [окно выбора цвета](../windows/colors-window-image-editor-for-icons.md) для создания образов.  
  
 Все цвета монохромный и 16 цветов изображения отображаются в окне выбора цвета палитры цветов. Помимо 16 стандартных цветов можно создавать свои собственные цвета. При изменении любого из цветов в палитре немедленно изменится на соответствующий цвет в изображении.  
  
 При работе с 256-цветного значка и курсор образы, свойство цвета в [окно свойств](/visualstudio/ide/reference/properties-window) используется. Дополнительные сведения см. в разделе [Создание 256-цветного значка или курсора](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Редактор изображений позволяет просматривать 32-разрядные изображения, но не позволяет их редактировать.  
  
 Можно также создать изображения True color. Тем не менее образцы цветов true не отображаются на полной палитре в окне выбора цвета; они отображаются только в области индикатора цвет переднего плана и фона. Значение true, цвета создаются с помощью [диалоговое окно «Выбор цвета»](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Дополнительные сведения см. в разделе [Настройка и изменение цветов](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Можно сохранить пользовательские палитры на диске и загружать их при необходимости. Цветовая палитра, которая недавно использованные сохраняется в реестре и автоматически загружается при очередном запуске Visual Studio.  
  
-   [Выбор основного цвета и цвета фона](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Заливка выделенной области изображения с цветом](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Выбор образца цвета из образа для использования в другом фрагменте](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [Выбор прозрачного и непрозрачного фона](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Преобразование цветов в выделенной области](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Настройка и изменение цветов](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Сохранение и загрузка различных цветовых палитр](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Окно "цвета"](../windows/colors-window-image-editor-for-icons.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   

