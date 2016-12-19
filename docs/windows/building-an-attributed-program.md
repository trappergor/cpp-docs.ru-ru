---
title: "Building an Attributed Program | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "tlb files"
  - "MIDL"
  - "MIDL, linker output"
  - "IDL files"
  - "tlb files, building attributed programs"
  - ".tlb files, building attributed programs"
  - "IDL files, building"
  - "attributes [C++], building type libraries and .idl files"
  - ".tlb files"
  - ".idl files, building"
  - "type libraries, linker options for building"
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Building an Attributed Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

После того как поместить атрибуты Visual C\+\+ в свой исходный код может потребоваться компилятора Visual C\+\+ создать библиотеку типов и idl\-файл.  Следующие параметры компоновщика, помогающие создавать файлы и .tlb idl.  
  
-   [\/IDLOUT](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)  
  
-   [\/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [\/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [\/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 Некоторые проекты содержат файлы несколько независимых idl.  Они используются для формирования двух или более файлов .tlb и при необходимости связать их в блок ресурса.  Этот скрипт в настоящее время не поддерживается в Visual C\+\+.  
  
 Кроме того, компоновщик Visual C\+\+ IDL\-родственные возвращает все данные атрибута в один файл MIDL.  Будет невозможно сформировать 2 библиотеки типов из одного проекта.  
  
## См. также  
 [Concepts](../windows/attributed-programming-concepts.md)