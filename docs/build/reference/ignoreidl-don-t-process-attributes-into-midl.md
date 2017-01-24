---
title: "/IGNOREIDL (не преобразовывать атрибуты в MIDL) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.IgnoreEmbeddedIDL"
  - "/ignoreidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNOREIDL - параметр компоновщика"
  - "IGNOREIDL - параметр компоновщика"
  - "-IGNOREIDL - параметр компоновщика"
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IGNOREIDL (не преобразовывать атрибуты в MIDL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNOREIDL  
```  
  
## Заметки  
 Параметр \/IGNOREIDL указывает на то, что [атрибуты IDL](../../windows/idl-attributes.md) в исходном коде не следует преобразовывать в файл IDL.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Щелкните страницу свойств **Внедренный IDL**.  
  
4.  Измените свойство **Игнорировать внедренные IDL**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [\/IDLOUT \(присвоение имен выходным файлам MIDL\)](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)   
 [\/TLBOUT \(задание имени TLB\-файла\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [\/MIDL \(Указание параметров командной строки MIDL\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)