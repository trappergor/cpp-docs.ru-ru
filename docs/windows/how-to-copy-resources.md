---
title: "How to: Copy Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.copying"
  - "vs.resvw.resource.copying"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], moving between files"
  - "resources [Visual Studio], copying"
  - "resource files, copying or moving resources between"
  - "resource files, tiling"
  - ".rc files, copying resources between"
  - "rc files, copying resources between"
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Copy Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вы может копировать ресурсы из одного файла в другой без изменений или [изменить язык или условие ресурса при копировании](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Вы можете легко копировать ресурсы из существующего ресурса или исполняемого файла в текущий ресурсный файл.  Чтобы это сделать, необходимо одновременно открыть оба файла, содержащие ресурсы, и перетащить элементы из одного файла в другой или выполнить операции копировать – вставить в этих двух файлах.  Этот метод работает для файлов скрипта ресурсов \(.rc\) и файлов ресурсных шаблонов \(.rct\), а также исполняемых файлов \(.exe\).  
  
> [!NOTE]
>  Visual C\+\+ включает образцы ресурсных файлов, которые вы можете использовать в собственных приложениях.  Дополнительные сведения см. в разделе [CLIPART: общие ресурсы](http://msdn.microsoft.com/ru-ru/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Вы можете использовать метод перетаскивания между двумя файлами .rc, открытыми [за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### Копирование ресурсов между файлами с помощью метода перетаскивания  
  
1.  Откройте оба файла ресурсов в автономном режиме \(дополнительную информацию см. в разделе [Просмотр ресурсов в .rc файле за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)\).  Например, откройте файлы Source1.rc и Source2.rc.  
  
2.  В первом RC\-файле щелкните ресурс, который необходимо скопировать.  Например, в файле Source1.rc, щелкните IDD\_DIALOG1.  
  
3.  Удерживая клавишу CTRL, перетащите ресурс во второй файл .rc.  Например, перетащите IDD\_DIALOG1 из файла Source1.rc в файл Source2.rc.  
  
    > [!NOTE]
    >  Перетаскивание ресурса без удерживания нажатой клавиши CTRL перемещает, а не копирует ресурс.  
  
### Копирование ресурсов методом копирования и вставки  
  
1.  Откройте оба файла ресурсов в автономном режиме \(дополнительную информацию см. в разделе [Просмотр ресурсов в .rc файле за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)\).  Например, файлы Source1.rc и Source2.rc.  
  
2.  В исходном файле, из которого вы хотите скопировать ресурс \(например, Source1.rc\), щелкните правой кнопкой мыши ресурс и выберите **Копировать** в контекстном меню.  
  
3.  Щелкните правой кнопкой мыши ресурсный файл, в который нужно добавить ресурс \(например, Source2.rc\).  В контекстном меню выберите пункт **Вставить**.  
  
    > [!NOTE]
    >  Вы не можете перетаскивать, копировать, вырезать и вставлять между ресурсными файлами проекта \(представление ресурса\) и автономными файлами .rc \(открытыми в окнах документа\).  Вы не сможете это сделать в предыдущих версиях продукта.  
  
    > [!NOTE]
    >  В процессе копирования ресурсов или объектов ресурса из одного RC\-файла в другой Visual C\+\+ может изменить значение или имя и значение копируемого ресурса во избежание конфликтов с именами и значениями ресурсов в файле назначения.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)