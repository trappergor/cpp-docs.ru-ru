---
title: "/MERGE (Слияние разделов) | Microsoft Docs"
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
  - "/merge"
  - "VC.Project.VCLinkerTool.MergeSections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MERGE - параметр компоновщика"
  - "MERGE - параметр компоновщика"
  - "-MERGE - параметр компоновщика"
  - "разделы"
  - "разделы, объединение"
  - "разделы, именование"
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MERGE (Слияние разделов)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MERGE:from=to  
```  
  
## Заметки  
 Параметр \/MERGE объединяет первый раздел \(*из*\) с помощью второго раздела \(*в*\), присваивая имя полученному разделу *в*.  Например, `/merge:.rdata=.text`.  
  
 Если второй раздел не существует оператор LINK переименовывает раздел *from* в *to*.  
  
 Параметр \/MERGE окажется полезным для создания VxD и замены имен, созданных компилятором.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Перейдите на страницу свойств **Дополнительно**.  
  
4.  Измените свойство **Слияние разделов**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)