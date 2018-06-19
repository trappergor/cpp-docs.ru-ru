---
title: Использование 256-цветной палитры (редактор изображений для значков) | Документы Microsoft
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
ms.openlocfilehash: 5dc78dfa5d549b37b99125cfcef5c25ae6c76b9e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890909"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>Использование 256-цветной палитры (редактор изображений для значков)
Чтобы рисовать, выбирая из 256-цветной палитры, необходимо выбрать цвета из палитры цветов в [окно выбора цвета](../windows/colors-window-image-editor-for-icons.md).  
  
### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Чтобы выбрать цвет из 256-цветной палитры для больших значков.  
  
1.  Выберите большого значка или курсора, или создайте новый большой значок или курсор.  
  
2.  Выберите цвет из 256 цветов, отображаемых в **цветов** палитру в **цветов** окна.  
  
     Цвет становится текущий цвет в палитре цветов **цветов** окна.  
  
    > [!NOTE]
    >  Начальный палитру, используемую для 256-цветного изображения соответствие цветовой палитре, возвращаемых CreateHalftonePalette Windows API. Чтобы предотвратить мерцание при реализации палитры все значки, предназначенные для оболочки Windows должны использовать эту палитру.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Создание 256-цветного значка или курсора](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)   
 [Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

