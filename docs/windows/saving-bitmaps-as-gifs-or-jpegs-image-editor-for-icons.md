---
title: Сохранение растровых изображений как изображений GIF или JPEG (редактор изображений для значков) | Документы Microsoft
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
ms.openlocfilehash: aed35f50e8cb874cea833439150b717034244b95
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890194"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>Сохранение растровых изображений как изображений GIF или JPEG (редактор изображений для значков)
При создании растрового изображения в формат растрового изображения (.bmp) создается изображение. Тем не менее, можно сохранить изображение в формате GIF или JPEG или в других графических форматов.  
  
> [!NOTE]
>  Этот процесс не применяется к значков и курсоров.  
  
### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Чтобы создать и сохранить растровое изображение как GIF или JPEG  
  
1.  Из **файл** меню, выберите **откройте**, нажмите кнопку **файл**.  
  
2.  В **диалоговое окно новый файл**, нажмите кнопку **Visual C++** папку, затем выберите **файл растрового изображения (.bmp)** в **шаблоны** и нажмите кнопку  **Откройте**.  
  
     Растровое изображение открывается в **изображения** редактора.  
  
3.  При необходимости, вносить изменения в созданное растровое изображение.  
  
4.  Все еще открыт в растровое изображение **изображения** редакторе щелкните **Сохранить *filename*.bmp как** на **файл** меню.  
  
5.  В **сохранить файл как** диалогового окна введите имя, назначаемое файла и расширение, определяющее формат файла, в **имя файла** поле. Например myfile.gif.  
  
     **Примечание** необходимо создать или открыть растрового изображения за пределами проекта, чтобы сохранить его в другом формате файла. При создании или открытии проекта, **Сохранить как** команда будет недоступна. Дополнительные сведения см. в разделе [Просмотр ресурсов в файле скрипта ресурсов за пределами проекта (автономный)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
6.  Нажмите кнопку **Сохранить**.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="see-also"></a>См. также  
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

