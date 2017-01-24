---
title: "&lt;para&gt; (Visual C++) | Microsoft Docs"
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
  - "<para>"
  - "para"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<para> - XML-тег C++"
  - "para - XML-тег C++"
ms.assetid: 35f2a1b3-bc14-4f13-bcb0-c39ccbf74d59
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;para&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<para\> используется внутри таких тегов, как [\<summary\>](../ide/summary-visual-cpp.md), [\<remarks\>](../ide/remarks-visual-cpp.md) или [\<returns\>](../ide/returns-visual-cpp.md), и позволяет структурировать текст.  
  
## Синтаксис  
  
```  
<para>content</para>  
```  
  
#### Параметры  
 `content`  
 Текст абзаца.  
  
## Заметки  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## Пример  
 Пример использования элемента \<para\> см. в разделе [\<summary\>](../ide/summary-visual-cpp.md).  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)