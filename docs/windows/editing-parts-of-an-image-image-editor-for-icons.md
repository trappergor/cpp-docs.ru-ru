---
title: Изменение фрагментов изображения (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1880853c63a236e824f9b59156181dccb2bba819
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647450"
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>Изменение фрагментов изображения (редактор изображений для значков)
Можно выполнять стандартные операции редактирования — вырезание, копирование, очистка и перемещение — на [выбора](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), является ли выделение всего изображения или только для части. Так как **изображение** редактор использует **буфер обмена Windows**, вы можете передать изображения между **изображение** редактора и других приложений для Windows.  
  
 Кроме того можно изменить размер выделения, ли он включает все изображение или только для части.  
  
### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>Вырезать выделенный фрагмент и переместить ее в буфер обмена  
  
1.  Нажмите кнопку **Вырезать** на **изменить** меню.  
  
### <a name="to-copy-the-selection"></a>Копирование выделенного фрагмента  
  
1.  Поместите курсор внутри границы выделения или любого другого расположения на нем Кроме маркеров.  
  
2.  Удерживая нажатой **Ctrl** клавишу перетащите в новое расположение. Область выделенного фрагмента не изменяется.  
  
3.  Копирование выделенного фрагмента в образ в текущем расположении, щелкните за пределами курсора выделения.  
  
### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Чтобы вставить содержимое буфера обмена в изображение  
  
1.  Из **изменить** меню, выберите **вставить**.  
  
     Содержимое буфера обмена, заключив его в рамки, отображаются в левом верхнем углу области.  
  
2.  Поместите указатель в пределах выделенной и перетащите изображение в нужное место в образе.  
  
3.  Чтобы закрепить изображение в новом расположении, щелкните за пределами границы выделения.  
  
### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Чтобы удалить текущее выделение без его перемещения в буфер обмена  
  
1.  Из **изменить** меню, выберите **удалить**.  
  
     Область исходного выделение заполняется текущим цветом фона.  
  
    > [!NOTE]
    >  Вы можете получить доступ к **Вырезать**, **копирования**, **вставить**, и **удалить** команд, щелкнув правой кнопкой мыши в **представление ресурсов** окна.  
  
### <a name="to-move-the-selection"></a>Для перемещения выделения  
  
1.  Поместите курсор внутри границы выделения или любого другого расположения на нем Кроме маркеров.  
  
2.  Перетащите его на новое место.  
  
3.  Чтобы закрепить элемент, выбранный в образ в новом расположении, щелкните за пределами границы выделения.  
  
 Дополнительные сведения о рисовании при помощи выделения, см. в разделе [Создание кисти Custom](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)