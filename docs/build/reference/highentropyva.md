---
title: "/HIGHENTROPYVA | Microsoft Docs"
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
  - "/HIGHENTROPYVA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HIGHENTROPYVA - параметр editbin"
  - "HIGHENTROPYVA - параметр editbin"
  - "-HIGHENTROPYVA - параметр editbin"
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HIGHENTROPYVA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, поддерживает ли исполняемый образ 64\-разрядную технологию ASLR с высокой энтропией.  
  
```  
  
/HIGHENTROPYVA[:NO]  
  
```  
  
## Заметки  
 Этот параметр изменяет заголовок DLL\- или EXE\-файла, указывая, поддерживается ли ASLR с 64\-разрядными адресами.  Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64\-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64\-разрядном виртуальном адресном пространстве.  Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.  
  
 По умолчанию компоновщик устанавливает этот параметр для 64\-разрядных исполняемых образов.  Чтобы задать этот параметр, необходимо также установить параметр [\/DYNAMICBASE](../../build/reference/dynamicbase.md).  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [\/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Способы защиты программного обеспечения Windows ISV](http://msdn.microsoft.com/library/bb430720.aspx)