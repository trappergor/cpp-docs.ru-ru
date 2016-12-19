---
title: "&lt;list&gt; (Visual C++) | Microsoft Docs"
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
  - "list"
  - "<list>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<list> - XML-тег C++"
  - "list - XML-тег C++"
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;list&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Блок \<listheader\> служит для задания строки заголовка таблицы или списка определений.  При определении таблицы достаточно указать запись для term в заголовке.  
  
## Синтаксис  
  
```  
<list type="bullet" | "number" | "table">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### Параметры  
 `term`  
 Термин, значение которого будет определено параметром `description`.  
  
 `description`  
 Элемент маркированного или нумерованного списка, определяющий значение параметра `term`.  
  
## Заметки  
 Каждый элемент в списке указывается в блоке \<item\>.  При создании списка определений необходимо указать и `term`, и `description`.  Однако для таблицы, маркированного или нумерованного списка достаточно указать только `description`.  
  
 Список или таблица могут содержать столько блоков \<item\>, сколько необходимо.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## Пример  
  
```  
// xml_list_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_list_tag.dll  
/// <remarks>Here is an example of a bulleted list:  
/// <list type="bullet">  
/// <item>  
/// <description>Item 1.</description>  
/// </item>  
/// <item>  
/// <description>Item 2.</description>  
/// </item>  
/// </list>  
/// </remarks>  
class MyClass {};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)