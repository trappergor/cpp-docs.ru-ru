---
title: Сохранение растровых изображений как изображений GIF или JPEG (редактор изображений для значков) | Документация Майкрософт
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
- .gif files, saving bitmaps as
- jpg files, saving bitmaps as
- jpeg files, saving bitmaps as
- .jpg files, saving bitmaps as
- Image editor [C++], converting image formats
- gif files, saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files, saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a87087b4ef51c016a5165f0d997824f174ca06c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608161"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>Сохранение растровых изображений как изображений GIF или JPEG (редактор изображений для значков)
При создании растрового изображения, в формат точечного рисунка (.bmp) создается изображение. Тем не менее, можно сохранить изображение в формате GIF или JPEG, или в других графических форматов.  
  
> [!NOTE]
>  Этот процесс не применяется к значки и курсоры.  
  
### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Чтобы создать и сохранить растровое изображение как GIF или JPEG  
  
1.  Из **файл** меню, выберите **откройте**, затем нажмите кнопку **файл**.  
  
2.  В **диалоговое окно нового файла**, нажмите кнопку **Visual C++** папку, затем выберите **файл точечного рисунка (.bmp)** в **шаблоны** поле и нажмите кнопку  **Откройте**.  
  
     Растровое изображение откроется в **изображение** редактора.  
  
3.  При необходимости, вносить изменения в созданное растровое изображение.  
  
4.  Все еще открыт в растровое изображение **изображение** редакторе щелкните **Сохранить *filename*.bmp как** на **файл** меню.  
  
5.  В **сохранить файл как** диалогового окна введите имя, назначаемое файла и расширение, определяющее формат файла, в **имя файла** поле. Например myfile.gif.  
  
     **Примечание** необходимо создать или открыть растрового изображения вне проекта, чтобы сохранить его как файл другого формата. Если создать или открыть его в проекте, **Сохранить как** команда будет недоступна. Дополнительные сведения см. в разделе [Просмотр ресурсов в файл скрипта ресурсов за пределами проекта (в автономном режиме)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
6.  Нажмите кнопку **Сохранить**.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="see-also"></a>См. также  
 [Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)