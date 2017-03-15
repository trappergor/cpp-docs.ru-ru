---
title: "&lt;permission&gt; (Visual C++) | Microsoft Docs"
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
  - "permission"
  - "<permission>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<permission> - XML-тег C++"
  - "permission - XML-тег C++"
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;permission&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<permission\> позволяет документу получил доступ к члену.  <xref:System.Security.PermissionSet> позволяет задать доступ к члену.  
  
## Синтаксис  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Параметры  
 `member`  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Компилятор проверяет, существует ли элемент кода и приводит `member` к каноническому имени элемента в выходных XML\-данных.  Заключить его в одинарные или двойные кавычки.  
  
 Компилятор выдает предупреждение, если не удается найти `member`.  
  
 Дополнительные сведения о создании cref\-ссылки на универсальный тип см. в разделе [\<see\>](../ide/see-visual-cpp.md).  
  
 `description`  
 Описание доступа к члену.  
  
## Заметки  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
 Компилятор C Visual C\+\+ пытается разрешить ссылки cref в одном прохождении через документирующие комментарии.  Поэтому при использовании правила поиска C, C\+\+, символ не найден компилятором, ссылка будет помечена как не разрешен.  Дополнительные сведения см. в разделе [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md).  
  
## Пример  
  
```  
// xml_permission_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_permission_tag.dll  
using namespace System;  
/// Text for class TestClass.  
public ref class TestClass {  
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>  
   void Test() {}  
};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)