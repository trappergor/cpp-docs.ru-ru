---
title: "ILK-файлы в качестве входных файлов компоновщика | Microsoft Docs"
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
  - "ILK-файлы"
  - "ILK-файлы"
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ILK-файлы в качестве входных файлов компоновщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В процессе инкрементного связывания программа LINK обновляет ILK\-файл состояния, который создается на первом этапе связывания.  ILK\-файлу присваивается имя, соответствующее базовому файлу с расширением EXE или DLL.  При выполнении последующих операций связывания содержимое ILK\-файла обновляется.  В случае отсутствия ILK\-файла программа LINK выполняет полное связывание и создает новый ILK\-файл.  Если ILK\-файл непригоден для использования, программа LINK выполняет неинкрементное связывание.  Дополнительные сведения об инкрементном связывании см. в описании [параметра инкрементного связывания \(\/INCREMENTAL\)](../../build/reference/incremental-link-incrementally.md).  
  
## См. также  
 [Входные LINK\-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)