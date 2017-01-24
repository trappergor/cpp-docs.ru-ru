---
title: "Choosing a Transparent or Opaque Background (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opaque backgrounds"
  - "background colors, images"
  - "colors [C++], image"
  - "Image editor [C++], transparent or opague backgrounds"
  - "background images"
  - "images [C++], transparency"
  - "images [C++], opaque background"
  - "transparent backgrounds"
  - "transparency, background"
  - "transparent backgrounds, images"
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Choosing a Transparent or Opaque Background (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда вы передвигаете или копируете выбранный фрагмент изображения, пиксели, которые совпадают по цвету с текущим фоном, по умолчанию становятся прозрачными, они не скрывают пиксели в целевом расположении.  
  
 Вы можете перейти от прозрачного фона \(установленного по умолчанию\) к непрозрачному и обратно.  Когда вы используете инструмент выделения, параметры **прозрачного фона** и **непрозрачного фона** появляются в селекторе параметров панели инструментов **редактора изображений** \(как показано ниже\).  
  
 ![Параметры фона — непрозрачный и прозрачный](../Image/vcImageEditorOpaqTranspBack.gif "vcImageEditorOpaqTranspBack")  
Параметры прозрачности и непрозрачности в панели инструментов редактора изображений  
  
### Переключиться между прозрачным и непрозрачным фоном  
  
1.  В панели инструментов **редактора изображений**, щелкните селектор **Параметр**, затем выберите нужный фон:  
  
    -   **Непрозрачный фон \(O\)**: существующее изображение замещается всеми частями выбранного фрагмента.  
  
    -   **Прозрачный фон \(T\)**: существующее изображение видно сквозь части выбранного фрагмента, совпадающего по цвету с фоном.  
  
 \- или \-  
  
-   В меню **Изображение** выберите или очистите **Нарисовать непрозрачный**.  
  
 Вы можете изменить цвет фона, когда выбранный фрагмент уже участвует в выполнении операции, определяющей, какие части изображения будут прозрачными.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 None  
  
## См. также  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)