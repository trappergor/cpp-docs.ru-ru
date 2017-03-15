---
title: "Настройка мастеров С++ с помощью общих функций JScript. | Microsoft Docs"
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
  - "методы мастера JScript, создание мастера С++"
ms.assetid: c602978f-a2c4-462f-85c3-50b5897bec46
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Настройка мастеров С++ с помощью общих функций JScript.
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании проекта мастера с помощью [Специального мастера](../ide/creating-a-custom-wizard.md) проект включает файл Сommon.js.  Если задать пользовательский интерфейс для мастера, проект также содержит HTML\-страницы, которые указывают язык скриптов JScript и включают файл Common.js следующим образом:  
  
```  
<SCRIPT ID="INCLUDE_COMMON" LANGUAGE ="JSCRIPT"></SCRIPT>  
```  
  
 Мастер также создает уникальный файл с именем Default.js.  В файле Default.js можно настроить собственные функции JScript.  Дополнительные сведения см. в разделе [Файл JScript](../ide/jscript-file.md).  
  
 Файл Common.js содержит функции, которые можно вызвать с любой HTML\-страницы мастера и из файла Default.js.  Если требуется использовать несколько одинаковых функций в различных мастерах, можно поместить эти функции в файл Common.js.  
  
## См. также  
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)