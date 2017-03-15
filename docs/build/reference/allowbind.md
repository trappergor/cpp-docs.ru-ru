---
title: "/ALLOWBIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALLOWBIND - параметр программы editbin"
  - "/ALLOWBIND - параметр программы editbin"
  - "-ALLOWBIND - параметр программы editbin"
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли библиотеки DLL можно выполнить привязку.  
  
```  
  
/ALLOWBIND[:NO]  
  
```  
  
## Заметки  
 **\/ALLOWBIND** несколько наборов параметров в заголовке библиотеки DLL, которая отображается для Bind.exe, что изображение может быть привязанным.  Привязка может разрешить изображение на загрузку быстрее, когда загрузчику не должен rebase и запуск относительной адресной привязки адреса для каждого указанного библиотеки DLL.  Может потребоваться не привязанным dll\-файл, если это цифров подписывать\- привязка что сигнатура.  Привязка не имеет силы, если randomization \(ASLR\) макета адресного пространства включен для образа с помощью **\/DYNAMICBASE** о версиях Windows, поддерживающих ASLR.  
  
 Используйте **\/ALLOWBIND:NO** для предотвращения Bind.exe привязки из библиотеки DLL.  
  
 Дополнительные сведения см. в параметр компоновщика [\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md).  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)