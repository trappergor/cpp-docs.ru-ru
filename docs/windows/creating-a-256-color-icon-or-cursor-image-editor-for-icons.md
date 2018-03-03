---
title: "Создание 256-цветного значка или курсора (редактор изображений для значков) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- cursors, color
- colors, icons
- colors, cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11c25c808ad9d1917413a66044e052e4c49ea584
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>Создание 256-цветного значка или курсора (редактор изображений для значков)
Редактор изображений, значков и курсоров может быть размера больших (64 × 64) с 256-цветной палитры для выбора. После создания ресурса выбирается стиль изображения устройства.  
  
### <a name="to-create-a-256-color-icon-or-cursor"></a>Создание 256-цветного значка или курсора  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл, а затем выберите **Вставка ресурса** в контекстном меню. (При наличии существующего ресурса изображения в RC-файле, такие как курсор, можно просто щелкнуть **курсор** папку и выберите **вставить курсор** в контекстном меню.)  
  
     **Примечание** Если проект еще не содержит RC-файл, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [Вставка ресурса-диалоговое окно](../windows/add-resource-dialog-box.md)выберите **значок** или **курсор** и нажмите кнопку **New**.  
  
3.  На **изображения** меню, нажмите кнопку **нового изображения устройства**.  
  
4.  Выберите нужный стиль 256-цветного изображения.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Требования**  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Использование 256-цветной палитры](../windows/using-the-256-color-palette-image-editor-for-icons.md)   
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

