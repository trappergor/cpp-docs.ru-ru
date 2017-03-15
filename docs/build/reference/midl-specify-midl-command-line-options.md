---
title: "/MIDL (Указание параметров командной строки MIDL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/midl"
  - "VC.Project.VCLinkerTool.MidlCommandFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MIDL - параметр компоновщика"
  - "MIDL"
  - "MIDL - параметр компоновщика"
  - "-MIDL - параметр компоновщика"
  - "MIDL, параметры командной строки"
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MIDL (Указание параметров командной строки MIDL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MIDL:@file  
```  
  
## Заметки  
 Здесь:  
  
 `file`  
 Имя файла, который содержит [Параметры командной строки MIDL](http://msdn.microsoft.com/library/windows/desktop/aa366839).  
  
## Заметки  
 Все параметры для преобразования IDL\-файла в TLB\-файл должны быть даны в `file`; параметры командной строки MIDL не могут быть указаны в командной строке компоновщика.  Если \/MIDL не указана, компилятор MIDL будет вызываться только с именем IDL\-файла без каких\-либо параметров.  
  
 Файл должен содержать один параметр командной строки MIDL для каждой строки.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Щелкните страницу свойств **Внедренный IDL**.  
  
4.  Измените свойство **Команды MIDL**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [\/IDLOUT \(присвоение имен выходным файлам MIDL\)](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)   
 [\/IGNOREIDL \(не преобразовывать атрибуты в MIDL\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/TLBOUT \(задание имени TLB\-файла\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)