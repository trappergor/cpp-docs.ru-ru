---
title: Использование 256-цветной палитры (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- colors, icons and cursors
- cursors, color
- color palettes, 256-color
- palettes, 256-color
- icons, color
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0287d27d975ce93e88a7a4b70a683188901ca958
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011820"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>Использование 256-цветной палитры (редактор изображений для значков)
Чтобы рисовать, выбирая с 256-цветной палитры, вам потребуется выбирать цвета из **цвета** палитру в [окно "цвета"](../windows/colors-window-image-editor-for-icons.md).  
  
### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Чтобы выбрать цвет из 256-цветной палитры для крупные значки  
  
1.  Выберите большой значка или курсора, или создайте большого значка или курсора.  
  
2.  Выбрать цвет из 256 цветов, отображаемых в **цвета** палитру в **цвета** окна.  
  
     Цвет становится текущий цвет в **цвета** палитру в **цвета** окна.  
  
    > [!NOTE]
    >  Начальная палитру, используемую для 256-цветных изображений соответствие цветовой палитре, возвращенный `CreateHalftonePalette` Windows API. Все значки, предназначенные для оболочки Windows следует использовать в этой палитре, чтобы предотвратить мерцание при реализации палитры.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Создание 256-цветного значка или курсора](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)   
 [Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)