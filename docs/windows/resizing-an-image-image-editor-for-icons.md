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
ms.openlocfilehash: 6e81ca5418782b993f406f33b0b207bc8acb5ba0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393663"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Изменение размера изображения (редактор изображений для значков)

Поведение **изображение** редактора при изменении размера изображения, зависит ли [выбранного](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) изображение целиком или только его часть.

Если выделение содержит только часть изображения, **изображение** редактор сокращает выделение, удалив строки или столбцы точек и заполнив освободившуюся область с текущим цветом фона, или она растягивается выделения на дублирование строк или столбцов пикселей.

Если выделение содержит всего изображения, **изображение** редактора либо сжимается и растянуть изображение, или обрезает его, а затем расширяет его.

Существует два механизма для изменения размеров изображения: маркеры и [окно "Свойства"](/visualstudio/ide/reference/properties-window). Можно перетащить маркеры изменения размера, чтобы изменить размер всех или части изображения. Маркеры, которые можно перетаскивать сплошной. Нельзя перетащить маркеры тянуть. Можно использовать **свойства** окно, чтобы изменить размер всего только, образ не выделенной области.

![Маркеры точечного рисунка](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
Маркеры изменения размера

> [!NOTE]
> Если у вас есть **плитку сетки** параметра, выбранного в [диалоговое окно параметров сетки](../windows/grid-settings-dialog-box-image-editor-for-icons.md), затем изменение размера позволяет выполнить привязку к следующей строке сетки плитки. Если только **пиксельную сетку** параметр выбран (по умолчанию), изменение размера позволяет выполнить привязку к доступным точкам.

- [Изменение размера всего изображения](../windows/resizing-an-entire-image-image-editor-for-icons.md)

- [Обрезание или расширение всего изображения](cropping-or-extending-an-entire-image-image-editor-for-icons.md)

- [Растяжение всего изображения и сжатие](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)

- [Растяжение и сжатие фрагмента изображения](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Редактор изображений для значков](../windows/image-editor-for-icons.md)