---
title: Изменение размера всего изображения (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- size [C++], images
- images [C++], resizing
- resizing images
ms.assetid: 10782937-7eb4-4340-bdec-618ee7d7904b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9104feac603819b9420d315e619182722c87474
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606222"
---
# <a name="resizing-an-entire-image-image-editor-for-icons"></a>Изменение размера всего изображения (редактор изображений для значков)
### <a name="to-resize-an-entire-image-using-the-properties-window"></a>Изменение размера всего изображения с помощью окна свойств  
  
1.  Откройте изображение, свойства которого требуется изменить.  
  
2.  В **ширины** и **высота** окнам в средах [окно "Свойства"](/visualstudio/ide/reference/properties-window), введите необходимые размеры.  
  
     Если вы увеличиваете размер изображения, редактор изображений расширяет изображение справа, сверху вниз, или оба и заполняет новую область с текущим цветом фона. Изображение не растягивается.  
  
     При уменьшении размера изображения, редактор изображений обрезает изображение справа или нижнего края или оба.  
  
    > [!NOTE]
    >  Чтобы изменить размер только всего изображения, не для частичного выделения можно использовать свойства Width и Height.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Изменение размера изображения](../windows/resizing-an-image-image-editor-for-icons.md)