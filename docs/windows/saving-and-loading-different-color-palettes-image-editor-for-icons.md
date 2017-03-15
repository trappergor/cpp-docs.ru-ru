---
title: "Saving and Loading Different Color Palettes (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.color"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "color palettes [C++]"
  - "palettes"
  - "palettes, Image editor"
  - "colors [C++], Image editor"
  - "Image editor [C++], palettes"
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Saving and Loading Different Color Palettes (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Палитру цветов, содержащую [пользовательские цвета](../windows/customizing-or-changing-colors-image-editor-for-icons.md), можно сохранять и загружать.  \(По умолчанию последняя использованная палитра цветов автоматически загружается при запуске Visual Studio.\)  
  
> [!TIP]
>  Поскольку в редакторе изображений отсутствуют средства для восстановления палитры цветов по умолчанию, следует сохранять такую палитру цветов под специальным именем, например, standard.pal или default.pal, чтобы можно было легко восстановить параметры по умолчанию.  
  
### Сохранение пользовательской палитры цветов  
  
1.  В меню **Изображение** выберите команду **Сохранить палитру**.  
  
2.  Перейдите в каталог, в который требуется сохранить палитру, и введите имя палитры.  
  
3.  Нажмите кнопку **Сохранить**.  
  
### Загрузка пользовательской палитры цветов  
  
1.  В меню **Изображение** выберите команду **Загрузить палитру**.  
  
2.  В [диалоговом окне "Загрузка палитры цветов"](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md) перейдите в нужный каталог и выберите палитру, которую требуется загрузить.  Палитры цветов сохраняются в файлах с расширением PAL.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в статье [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Нет  
  
## См. также  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)