---
title: "Moving a String from One Resource File to Another | Microsoft Docs"
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
  - "strings [C++], moving between files"
  - "resource script files, moving strings"
  - "string editing, moving strings between resources"
  - "String editor, moving strings between files"
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Moving a String from One Resource File to Another
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Перемещение строки из одного файла скрипта ресурсов в другой  
  
1.  Откройте таблицы строк в обоих RC\-файлах.  \(Дополнительные сведения см. в разделе [Просмотр ресурсов в файле скрипта ресурсов за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).\)  
  
    > [!NOTE]
    >  Если в проекте нет RC\-файла, см. раздел [Создание нового файла скрипта ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Щелкните правой кнопкой мыши строку, которую необходимо переместить, и выберите команду **Вырезать** в контекстном меню.  
  
3.  Поместите курсор в окно **редактора строк**, в котором необходимо вставить строку.  
  
4.  В RC\-файле, в который необходимо вставить строку, щелкните правой кнопкой мыши и выберите в контекстном меню команду **Вставить**.  
  
    > [!NOTE]
    >  Если **идентификатор** или **значение** перемещаемой строки конфликтует с уже существующими в конечном файле **идентификаторами** или **значениями**, то **идентификатор** или **значение** перемещенной строки будет изменено.  Если в конечном файле есть строка с таким же **идентификатором**, **идентификатор** перемещенной строки будет изменен.  Если в конечном файле есть строка с таким же **значением**, **значение** перемещенной строки будет изменено.  
  
 Сведения о добавлении ресурсов в управляемые проекты \(предназначенные для выполнения в общеязыковой среде CLR\) см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [String Editor](../mfc/string-editor.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Настройка макетов окон](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md)   
 [Строки](_win32_Strings)   
 [О строках](_win32_About_Strings_cpp)