---
title: Изменение фрагментов изображения (редактор изображений для значков) | Документы Microsoft
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
ms.openlocfilehash: b33a591a2f38062b5eaf81b0f56ab73a36f4c90c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>Изменение фрагментов изображения (редактор изображений для значков)
Можно выполнять стандартные операции редактирования — вырезание, копирование, очистка и перемещение — на [выбора](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), является ли выделение всего изображения или только для части. Поскольку редактор изображений использует буфер обмена Windows, можно передавать изображения между редактора изображений и других приложений для Windows.  
  
 Кроме того можно изменить выбор, ли он включает все изображение или только часть.  
  
### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>Вырезать выделенный фрагмент и поместить его в буфер обмена  
  
1.  Нажмите кнопку **Вырезать** на **изменить** меню.  
  
### <a name="to-copy-the-selection"></a>Копирование выделенного фрагмента  
  
1.  Поместите указатель в пределах выделенной области или в любом месте на нем Кроме маркеров.  
  
2.  Удерживайте клавишу **CTRL** ключа, перетащите его на новое место. Область в исходном изображении не изменяется.  
  
3.  Копирование выделенного фрагмента в изображение в текущем местоположении, щелкните за пределами курсора выделенной области.  
  
### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Чтобы вставить содержимое буфера обмена в изображение  
  
1.  Из **изменить** меню, выберите **вставить**.  
  
     Содержимое буфера обмена, заключенное в рамки, отображаются в левом верхнем углу области.  
  
2.  Поместите указатель в пределах выделенной и перетащите изображение в нужное место в образе.  
  
3.  Чтобы закрепить изображение в новом месте, щелкните за пределами границ выделенной области.  
  
### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Чтобы удалить выбранные элементы без его перемещения в буфер обмена  
  
1.  Из **изменить** меню, выберите **удалить**.  
  
     Заполнения исходной области выделения цветом фона.  
  
    > [!NOTE]
    >  Доступ к вырезания, копирования, вставки и удаления команд, щелкните правой кнопкой мыши в окне представления ресурсов.  
  
### <a name="to-move-the-selection"></a>Чтобы переместить выбранный элемент  
  
1.  Поместите указатель в пределах выделенной области или в любом месте на нем Кроме маркеров.  
  
2.  Перетащите его на новое место.  
  
3.  Чтобы закрепить выделенную область изображения в новом месте, щелкните за пределами границ выделенной области.  
  
 Дополнительные сведения о рисовании при помощи выделения см. в разделе [Создание настраиваемых кисти](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

