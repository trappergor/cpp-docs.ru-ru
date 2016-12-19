---
title: "Типы значений и их режимы работы (C++/CLI) | Microsoft Docs"
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
  - "типы значений"
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Типы значений и их режимы работы (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Типы значений претерпели значительные изменения, начиная с управляемых расширений для C\+\+ и заканчивая [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  В этом разделе мы рассмотрим перечисляемый тип среды CLR, тип класса значения, упаковку\-преобразование, доступ к упакованным экземплярам в куче CLR, а также внутренние и закрепляющие указатели.  В данной области произошли масштабные трансформации языков программирования.  
  
## Содержание  
 [CLR Enum Type](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Изменения в объявлении и режимах перечисляемых элементов.  
  
 [Неявная упаковка\-преобразование типов значений](../dotnet/implicit-boxing-of-value-types.md)  
 Причины неявной упаковки\-преобразования типов значений и последующие изменения в режимах работы.  
  
 [Дескриптор отслеживания для упакованных значений](../dotnet/a-tracking-handle-to-a-boxed-value.md)  
 Способ преобразования неявной упаковки\-преобразования типов значения с дескриптора отслеживания в упакованный объект\-значение.  
  
 [Семантика типа значения](../Topic/Value%20Type%20Semantics.md)  
 Изменения в семантике типа значения, в том числе в унаследованных виртуальных методах, в конструкторах, созданных по умолчанию для класса, а также во внутренних и закрепляющих указателях.  
  
## См. также  
 [Основы миграции C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)