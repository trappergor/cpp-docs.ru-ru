---
title: "STUB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "STUB"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STUB - оператор DEF-файла"
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# STUB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При использовании в файле определения модуля, собирающего драйвер виртуального устройства \(VxD\) данный параметр позволяет указать имя файла, содержащего структуру IMAGE\_DOS\_HEADER \(определенную в файле WINNT.H\), который будет использоваться в драйвере виртуального устройства \(VxD\) вместо заголовка по умолчанию.  
  
```  
STUB:filename  
```  
  
## Заметки  
 Указать параметр *filename* также можно с помощью параметра компоновщика [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md).  
  
 Параметр STUB допустим в файле определении модуля только при построении драйвера виртуального устройства.  
  
## См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)