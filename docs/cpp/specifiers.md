---
title: "Спецификаторы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "спецификаторы объявления"
  - "объявления, описатели"
  - "описатели, в объявлениях"
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Спецификаторы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается компонент *decl\-specifiers* \(описатели объявления\) [объявления](../misc/declarations.md).  
  
 Следующие местозаполнители и ключевые слова языка являются определителями объявления:  
  
 *описатель\_класса\_хранения \(storage\-class\-specifier\)*  
  
 *описатель\_типа \(type\-specifier\)*  
  
 *описатель\_функции \(function\-specifier\)*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/ru-ru/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [\_\_declspec](../cpp/declspec.md) `(` *последовательность\_модификаторов\_расширенного\_объявления* \(extended\-decl\-modifier\-seq\) `)`  
  
## Заметки  
 Часть *decl\-specifiers* объявления является самой длинной последовательностью *описателей объявления*, которая может использоваться для обозначения имени типа и не включать модификаторы указателя или ссылки.  Остальная часть объявления является *декларатором*, включая представленное имя.  
  
 В приведенной ниже таблице представлены четыре объявления и далее — компоненты *decl\-specifers* и *декларатор* каждого объявления в отдельности.  
  
|Объявление|*Описатели объявления*|`declarator`|  
|----------------|----------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 Поскольку `signed`, `unsigned`, `long` и `short` подразумевают `int`, имя `typedef`, следующее за одним из этих ключевых слов, принимается в качестве члена *список\_деклараторов* \(declarator\-list\), а не *описатели\_объявления* \(decl\-specifiers\).  
  
> [!NOTE]
>  Поскольку имя можно объявить повторно, его интерпретация относится к самой последней декларации в текущей области.  Повторное объявление может повлиять на способ интерпретации имен компилятором, в особенности — имен `typedef`.  
  
## См. также  
 [Объявления](../misc/declarations.md)