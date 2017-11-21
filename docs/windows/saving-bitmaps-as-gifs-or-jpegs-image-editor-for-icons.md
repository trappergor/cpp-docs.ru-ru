---
title: "Сохранение растровых изображений как изображений GIF или JPEG (редактор изображений для значков) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.image.editing
dev_langs: C++
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
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f6bded97e27101981c17dce51d7fc9ecb9cd8d55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="see-also"></a>См. также  
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

