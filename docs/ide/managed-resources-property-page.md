---
title: "Страница свойств управляемых ресурсов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCManagedResourceCompilerTool.ResourceFileName"
  - "VC.Project.VCManagedResourceCompilerTool.OutputFileName"
  - "VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "страница свойств управляемых ресурсов"
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Страница свойств управляемых ресурсов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Включает параметры компилятора ресурсов.  
  
 Страница свойств **Управляемые ресурсы** содержит следующие свойства:  
  
 **Логическое имя ресурса**  
 Задает *логическое имя* созданного промежуточного файла ресурсов \(с расширением RESOURCES\).  Логическое имя — это имя, используемое для загрузки ресурса.  Если логическое имя не указано, то в качестве логического имени используется имя файла ресурсов \(с расширением RESX\).  
  
 **Имя выходного файла**  
 Указывает имя окончательного выходного файла, в создании которого принимает участие файл ресурсов \(с расширением RESX\).  
  
 **Локализованные ресурсы по умолчанию**  
 Указывает, относится ли заданный RESX\-файл к ресурсам по умолчанию или к вспомогательной библиотеке DLL.  
  
 Дополнительные сведения о доступе к страницы свойств **Управляемые ресурсы** см. в разделе [Практическое руководство. Задание свойств проекта при помощи страниц свойств](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md).  
  
## См. также  
 [Using RC \(The RC Command Line\)](http://msdn.microsoft.com/library/windows/desktop/aa381055)   
 [Страницы свойств](../ide/property-pages-visual-cpp.md)   
 [\/ASSEMBLYRESOURCE \(внедрение управляемого ресурса\)](../build/reference/assemblyresource-embed-a-managed-resource.md)