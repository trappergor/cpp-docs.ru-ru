---
title: "Параметр /FD (минимальное перестроение интерфейса IDE) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/FD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FD - параметр компилятора [C++]"
  - "FD - параметр компилятора [C++]"
  - "-FD - параметр компилятора [C++]"
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Параметр /FD (минимальное перестроение интерфейса IDE)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр **\/FD** доступен пользователям только на странице [Командная строка](../../ide/command-line-property-pages.md) в диалоговом окне **Страницы свойств** проекта C\+\+, если не выбран параметр [\/Gm \(включение минимального перестроения\)](../../build/reference/gm-enable-minimal-rebuild.md).  Параметр **\/FD** действует только при использовании в среде разработки.  Параметр **\/FD** не предоставляется в выходных данных команды **cl \/?**.  
  
 Если в среде разработки не включить параметр **\/Gm**, будет использоваться параметр **\/FD**.  Параметр **\/FD** обеспечивает наличие достаточных сведений о зависимостях в IDB\-файле.  Параметр **\/FD** используется только в среде разработки и не может применяться в командной строке или в скрипте построения.  
  
## См. также  
 [Параметры выходного файла \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)