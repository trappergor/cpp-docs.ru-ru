---
title: "Resource Files (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio]"
  - ".rc files"
  - "resource files"
  - "resource script files"
  - "resource script files, Win-32 based applications"
  - "resource script files, files updated when editing resources"
  - "resources [Visual Studio], types of resource files"
  - "rct files"
  - "resources [C++]"
  - "rc files"
  - "resource files, types of"
  - ".rct files"
  - "resource script files, unsupported types"
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Resource Files (Visual Studio)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Этот материал относится к классическим приложениям Windows. Сведения о ресурсах в приложениях [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] см. в разделе [Определение ресурсов приложения](http://msdn.microsoft.com/ru-ru/476ea844-632c-4467-9ce3-966be1350dd4).  
>   
>  Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Так как в проектах на языках программирования .NET не используются файлы описания ресурсов, ресурсы необходимо открывать из **обозревателя решений**. Для работы с файлами ресурсов в управляемых проектах можно использовать [редактор изображений](../mfc/image-editor-for-icons.md) и [двоичный редактор](../mfc/binary-editor.md). Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация форм Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Термин "файл ресурсов" может относиться к ряду типов файлов, включая следующие:  
  
-   файл описания ресурсов программы \(RC\);  
  
-   файл шаблона ресурсов \(RCT\);  
  
-   ресурс, существующий в виде отдельного файла, например файл с растровым изображением, значком или курсором, на который имеется ссылка в файле RC;  
  
-   файл заголовка, созданный средой разработки, например Resource.h, на который есть ссылка в файле RC.  
  
 Ресурсы также могут находиться в [файлах других типов](../windows/editable-file-types-for-resources.md), например EXE, DLL и RES. Вы можете работать с ресурсами и файлами ресурсов, включенными в текущий проект или не являющимися его частью. Также можно работать с файлами ресурсов, которые не были созданы в среде разработки Visual Studio. Например, с их помощью можно выполнять следующее.  
  
-   Работать с вложенными и условно включенными файлами ресурсов.  
  
-   Обновлять существующие ресурсы или преобразовывать их в формат Visual C\+\+.  
  
-   Импортировать графические ресурсы в текущий файл ресурсов или экспортировать их из него.  
  
-   Включать общие или доступные только для чтения идентификаторы \(символы\), которые нельзя изменить с помощью среды разработки.  
  
-   Включать в исполняемый файл \(EXE\) ресурсы, которые не требуют редактирования \(или не должны редактироваться\) в процессе работы над текущим проектом, например ресурсы, используемые одновременно в нескольких проектах.  
  
-   Включать типы ресурсов, не поддерживаемые средой разработки.  
  
 В этом разделе рассматриваются следующие задачи:  
  
-   [Создание файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md)  
  
-   [Создание ресурса](../windows/how-to-create-a-resource.md)  
  
-   [Просмотр ресурсов в файле описания ресурсов](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [Открытие файла описания ресурсов в текстовом формате](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [Включение ресурсов во время компиляции](../Topic/How%20to:%20Include%20Resources%20at%20Compile%20Time.md)  
  
-   [Копирование ресурсов](../windows/how-to-copy-resources.md)  
  
-   [Использование шаблонов ресурсов \(RCT\)](../Topic/How%20to:%20Use%20Resource%20Templates.md)  
  
-   [Импорт и экспорт ресурсов](../windows/how-to-import-and-export-resources.md)  
  
-   [Редактируемые типы файлов для ресурсов](../windows/editable-file-types-for-resources.md)  
  
-   [Файлы, на которые влияет редактирование ресурсов](../Topic/Files%20Affected%20by%20Resource%20Editing.md)  
  
## Требования  
 Win32  
  
## См. также  
 [Resource Editors](../mfc/resource-editors.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Меню и другие ресурсы](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)