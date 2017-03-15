---
title: "/DYNAMICBASE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dynamicbase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE - параметр программы editbin"
  - "DYNAMICBASE - параметр программы editbin"
  - "-DYNAMICBASE - параметр программы editbin"
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /DYNAMICBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, можно ли случайным образом изменять базовый адрес исполняемого образа во время загрузки с помощью технологии ASLR.  
  
## Синтаксис  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## Заметки  
 По умолчанию компоновщик задает параметр **\/DYNAMICBASE**.  
  
 Этот параметр изменяет заголовок исполняемого образа, чтобы указать, может ли загрузчик случайным образом изменять базовый адрес образа во время загрузки.  
  
 ASLR поддерживается в Windows Vista, Windows Server 2008, Windows 7, Windows 8 и Windows Server 2012.  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [Способы защиты программного обеспечения Windows ISV](http://msdn.microsoft.com/library/bb430720.aspx)