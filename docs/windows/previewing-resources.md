---
title: "Previewing Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.previewing"
  - "vs.resvw.resource.previewing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "resource previews"
  - "code, viewing"
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Previewing Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функция предварительного просмотра позволяет просматривать графические ресурсы, не открывая их.  Предварительный просмотр также можно использовать после компиляции исполняющихся файлов, когда идентификаторы ресурсов меняются на цифры.  Поскольку по цифрам довольно затруднительно ориентироваться, для идентификации ресурсов можно использовать функцию предварительного просмотра.  
  
 Можно предварительно просматривать ресурсы следующих типов:  
  
-   Растровое изображение  
  
-   Диалоговый  
  
-   Значок  
  
-   Меню  
  
-   Курсор  
  
-   Панель инструментов  
  
 Функцию предварительного просмотра нельзя применить к ресурсам сочетаний клавиш, манифестов, таблиц строк, а также к ресурсам сведений об информации.  
  
### Предварительный просмотр ресурсов  
  
1.  В [представлении ресурсов](../windows/resource-view-window.md) или в окне документа выберите ресурс, например IDD\_ABOUTBOX.  
  
     **Примечание.** Если в проекте еще нет RC\-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [окне свойств](../Topic/Properties%20Window.md) нажмите кнопку **Страницы свойств**.  
  
     \- или \-  
  
3.  В меню **Вид** выберите команду **Страницы свойств**.  
  
     Откроется страница свойств ресурса, на которой в области предварительного просмотра будет отображаться ресурс.  Для перемещения по дереву элементов управления в представлении ресурсов или в окне документа можно использовать клавиши СТРЕЛКА ВВЕРХ и СТРЕЛКА ВНИЗ.  Страница свойств при этом останется открытой и на ней будет отображаться любой ресурс, на котором будет установлен фокус, при условии, что этот ресурс поддерживает функцию предварительного просмотра.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Editors](../mfc/resource-editors.md)