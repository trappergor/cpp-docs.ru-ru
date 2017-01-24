---
title: "Директивы шаблона | Microsoft Docs"
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
  - "[!else] - директива шаблонов"
  - "[!endif] - директива шаблонов"
  - "[!endloop] - директива шаблонов"
  - "[!if] - директива шаблонов"
  - "[!loop] - директива шаблонов"
  - "[!output] - директива шаблонов"
  - "пользовательские мастера, директивы шаблона"
  - "директивы, директивы шаблона"
  - "else - директива ([!else])"
  - "endif - директива ([!endif])"
  - "endloop - директива ([!endloop])"
  - "if - директива ([!if])"
  - "loop - директива ([!loop])"
  - "output - директива ([!output])"
  - "директивы шаблона"
ms.assetid: b6204153-813a-423c-b044-e39c352cc5af
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Директивы шаблона
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ниже перечислены директивы шаблона, которые можно использовать в [файле шаблона](../ide/template-files.md) мастера и [файле templates.inf](../Topic/Templates.inf%20File.md) для настройки мастера.  
  
|Директива|Описание|  
|---------------|--------------|  
|\[\!  if \]|Начинает управляющую структуру для проверки условия.|  
|\[\!  else \]|Часть управляющей структуры \[\!  if \].  Проверяет другое условие.|  
|\[\!  endif \]|Завершает определение структуры \[\!  if \].|  
|\[\!  output \]|Может использоваться следующими двумя способами:<br /><br /> -   \[\!  output "строка" \] предоставляет строку.<br />-   \[\!  output SYMBOL\_STRING \] предоставляет значение символа SYMBOL\_STRING.|  
|\[\!  loop \]|Может использоваться следующими двумя способами:<br /><br /> -   \[\!  loop \= 5 \]<br />-   \[\!  loop \= *NUM\_OF\_PAGES* \], где *NUM\_OF\_PAGES* является символом с числовым значением.|  
|\[\!  endloop \]|Завершает структуру цикла.|  
  
 Левая скобка \(\[\), за которой следует восклицательный знак \(\!\), обозначает начало директивы шаблона.  Правая скобка обозначает завершение директивы шаблона.  Синтаксис любой директивы должен выглядеть следующим образом:  
  
```  
[!directive params]  
```  
  
 Пробел или знак, который не является идентификатором, необходимы только между *директивой* и *параметрами*.  
  
## Пример  
  
```  
[!if SAMPLE_RADIO_OPTION1]  
You have checked the option 'Sample radio button option 1'  
[!else]  
You have checked the option 'Sample radio button option 2'  
[!endif]  
```  
  
 С вышеперечисленными директивами в файле шаблона можно использовать следующие операторы.  
  
```  
+  
-     
=  
!=     
==     
||     
&&    
!  
```  
  
## Пример  
  
```  
[!if SYMBOL_STRING != 0]  
```  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)