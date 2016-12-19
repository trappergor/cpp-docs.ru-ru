---
title: "Ошибка средств компоновщика LNK1309 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1309"
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

обнаружен модуль "type1"; недоступен при подключении \/CLRIMAGETYPE:type2  
  
 Затребован тип\-изображение в среде CLR с помощью **\/CLRIMAGETYPE**, но компоновщику не удается произвести изображение требуемого тип, так как один или несколько модулей несовместимы с этим типом.  
  
 Например, можно увидеть LNK1309, если указать **\/CLRIMAGETYPE:safe** и передать построение модулей с помощью **\/clr:pure**.  
  
 Также можно увидеть LNK1309, если попытаться создать в среде CLR с частичным доверием чистое приложение с помощью ptrustu\[d\].lib.  Дополнительные сведения о том, как создать частично безопасное приложение, см.: [Практическое руководство. Создание приложения с частичным доверием путем удаления зависимости от библиотеки DLL CRT](../../dotnet/create-a-partially-trusted-application.md).  
  
 Дополнительные сведения см. в разделах [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) и [\/CLRIMAGETYPE \(указание типа образа среды CLR\)](../Topic/-CLRIMAGETYPE%20\(Specify%20Type%20of%20CLR%20Image\).md).