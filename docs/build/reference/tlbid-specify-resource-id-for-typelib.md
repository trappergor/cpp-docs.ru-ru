---
title: "/TLBID (указать идентификатор ресурса для TypeLib) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/tlbid"
  - "VC.Project.VCLinkerTool.TypeLibraryResourceID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TLB-файлы, идентификатор ресурса - указание"
  - "/TLBID - параметр компоновщика"
  - "TLB-файлы, идентификатор ресурса - указание"
  - "TLBID - параметр компоновщика"
  - "-TLBID - параметр компоновщика"
  - "библиотеки типов, идентификатор ресурса - указание"
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /TLBID (указать идентификатор ресурса для TypeLib)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBID:id  
```  
  
## Заметки  
 Здесь:  
  
 `id`  
 Определенное пользователем значение для библиотеки типов, созданной компоновщиком.  Переопределяет идентификатор ресурса по умолчанию 1.  
  
## Заметки  
 При компиляции программы, использующей атрибуты, компоновщик создаст библиотеку типов.  Компоновщик назначит идентификатор ресурса 1 библиотеке типов.  
  
 Если этот идентификатор ресурса конфликтует с одним из существующих ресурсов, можно указать другой идентификатор с помощью \/TLBID.  Диапазон значений, которые можно передать идентификатору `id`, — от 1 до 65535.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Щелкните страницу свойств **Внедренный IDL**.  
  
4.  Измените свойство **Идентификатор ресурса TypeLib**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)