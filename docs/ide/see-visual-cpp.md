---
title: "&lt;see&gt; (Visual C++) | Microsoft Docs"
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
  - "<see>"
  - "see"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<see> - XML-тег C++"
  - "see - XML-тег C++"
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;see&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<see\> позволяет определить ссылку в тексте.  Используйте [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md) для отображения текста, возможно, появится в разделе " см. также ".  
  
## Синтаксис  
  
```  
<see cref="member"/>  
```  
  
#### Параметры  
 `member`  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Заключить его в одинарные или двойные кавычки.  
  
 Компилятор проверяет, что данный элемент кода существует и позволяет `member` с именем элемента в выходных XML\-данных.  Компилятор выдает предупреждение, если не удается найти `member`.  
  
## Заметки  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
 В разделе [\<summary\>](../ide/summary-visual-cpp.md) пример использования \<see\>.  
  
 Компилятор C Visual C\+\+ пытается разрешить ссылки cref в одном прохождении через документирующие комментарии.  Поэтому при использовании правила поиска C, C\+\+, символ не найден компилятором, ссылка будет помечена как не разрешен.  Дополнительные сведения см. в разделе [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md).  
  
## Пример  
 В следующем примере показано, как можно сделать ссылку на универсальному типу, то cref, что компилятор разрешает ссылку.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)