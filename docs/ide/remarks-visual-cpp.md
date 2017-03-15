---
title: "&lt;remarks&gt; (Visual C++) | Microsoft Docs"
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
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<remarks> - XML-тег C++"
  - "remarks - XML-тег C++"
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;remarks&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<remarks\> используется для добавления сведений о типе, дополняющих сведения, указанные в [\<summary\>](../ide/summary-visual-cpp.md).  Эти сведения отображаются в [Обозреватель объектов](http://msdn.microsoft.com/ru-ru/f89acfc5-1152-413d-9f56-3dc16e3f0470) и в веб\-отчет комментариев кода.  
  
## Синтаксис  
  
```  
<remarks>description</remarks>  
```  
  
#### Параметры  
 `description`  
 Описание члена.  
  
## Заметки  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## Пример  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)