---
title: "&lt;exception&gt; (Visual C++) | Microsoft Docs"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<exception> - XML-тег C++"
  - "exception - XML-тег C++"
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;exception&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<exception\> служит для указания возможных исключений.  Этот тег применяется к определению метода.  
  
## Синтаксис  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Параметры  
 `member`  
 Ссылка на исключение, которое доступно из текущей среды компиляции.  С помощью правил поиска имени, компилятор проверяет, что данное исключение существует, и преобразует `member` в каноническое имя элемента в выходных XML\-данных.  Компилятор выдает предупреждение, если не удается найти `member`.  
  
 Заключить его в одинарные или двойные кавычки.  
  
 Дополнительные сведения о создании cref\-ссылки на универсальный тип см. в разделе [\<see\>](../ide/see-visual-cpp.md).  
  
 `description`  
 Описание  
  
## Заметки  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
 Компилятор C Visual C\+\+ пытается разрешить ссылки cref в одном прохождении через документирующие комментарии.  Поэтому при использовании правила поиска C, C\+\+, символ не найден компилятором, ссылка будет помечена как не разрешен.  Дополнительные сведения см. в разделе [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md).  
  
## Пример  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)