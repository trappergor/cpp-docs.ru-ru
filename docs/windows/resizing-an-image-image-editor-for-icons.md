---
title: Изменение размера изображения (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41494e8b88f41c4c842e95e9f8a9f5da0247739f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605647"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Изменение размера изображения (редактор изображений для значков)
Поведение редактора изображений при изменении размера изображения, зависит от того, ли [выбранного](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) изображение целиком или только его часть.  
  
 Если выделение содержит только часть изображения, редактор изображений сокращает выделение, удалив строки или столбцы точек и заполнив освободившуюся область с текущим цветом фона, либо растягивает выделение путем дублирования строк или столбцов точек.  
  
 Если выделение содержит все изображение, редактор изображений либо сжимает и растянуть изображение, или обрезает его и расширяет его.  
  
 Существует два механизма для изменения размеров изображения: маркеры и [окно "Свойства"](/visualstudio/ide/reference/properties-window). Можно перетащить маркеры изменения размера, чтобы изменить размер всех или части изображения. Маркеры, которые можно перетаскивать сплошной. Нельзя перетащить маркеры тянуть. Можно использовать окно свойств для изменения размера всего изображения, не выбранной части.  
  
 ![Маркеры точечного рисунка](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
Маркеры изменения размера  
  
> [!NOTE]
>  Если у вас есть параметр плитку сетки в [диалоговое окно параметров сетки](../windows/grid-settings-dialog-box-image-editor-for-icons.md), затем изменение размера позволяет выполнить привязку к следующей строке сетки плитки. Если только Точечная сетка выбран (по умолчанию), изменение размера позволяет выполнить привязку к доступным точкам.  
  
-   [Изменение размера всего изображения](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Обрезание или расширение всего изображения](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Растяжение всего изображения и сжатие](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Растяжение и сжатие фрагмента изображения](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)