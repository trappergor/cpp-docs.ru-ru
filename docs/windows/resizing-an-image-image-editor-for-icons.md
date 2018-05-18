---
title: Изменение размера изображения (редактор изображений для значков) | Документы Microsoft
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
ms.openlocfilehash: c6636e1f92907c301c6e66abd63f744375bffeb8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Изменение размера изображения (редактор изображений для значков)
Поведение редактора изображения при изменении размера изображения зависит ли [выбранного](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) всего изображения или только его фрагмент.  
  
 Если выделена только часть изображения, редактор изображений может уменьшить выделенную область, удалив строки или столбцы точек и заполнив освободившуюся область с текущим цветом фона или его растягивает выделение путем дублирования строк или столбцов пикселей.  
  
 Если выделено все изображение, редактор изображений либо сжимает и растянуть изображение, или обрезает и расширяет его.  
  
 Существует два механизма изменить размеры изображения: маркеры изменения размера и [окно свойств](/visualstudio/ide/reference/properties-window). Можно перетаскивать маркеры изменения размера, чтобы изменить размер всех или части изображения. Маркеры изменения размера, которые можно перетащить сплошная. Нельзя перетащить маркеры, которые являются пустыми. Можно использовать в окне свойств изменение размера всего изображения не выделенной области.  
  
 ![Маркеры точечного рисунка](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
Маркеры изменения размера  
  
> [!NOTE]
>  Если у вас есть параметр плитку сетки в [параметры сетки-диалоговое окно](../windows/grid-settings-dialog-box-image-editor-for-icons.md), затем изменить ее размер позволяет выполнить привязку к следующей строке сетки плитки. Если только Точечная сетка выбран (по умолчанию), маркер может перемещаться доступным точкам.  
  
-   [Изменение размера всего изображения](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Обрезание или расширение всего изображения](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Растяжение всего изображения и](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Растяжение и сжатие фрагмента изображения](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

