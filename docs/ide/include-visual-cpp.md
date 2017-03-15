---
title: "&lt;include&gt; (Visual C++) | Microsoft Docs"
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
  - "include"
  - "<include>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<include> - XML-тег C++"
  - "include - XML-тег C++"
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;include&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте тег \<include\> для ссылок на комментарии в другом файле, описывающем типы и элементы в исходном коде.  Это является альтернативой помещению комментариев документации непосредственно в файле исходного кода.  Например, можно использовать \<include\>, чтобы вставить стандартные комментарии "котельного листа", которые используются во всех пользовательских команда или компании.  
  
## Синтаксис  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### Параметры  
 `filename`  
 Имя файла, содержащего документацию.  Имя файла может быть дополнено путем.  Заключить его в одинарные или двойные кавычки.  Компилятор выдает предупреждение, если не удается найти `filename`.  
  
 `tagpath`  
 Допустимое выражение XPath, которое выбирает нужный после внесения набор содержит в файле.  
  
 `name`  
 Спецификатор имени в теге, который предшествует комментариям; `name` будет иметь `id`.  
  
 `id`  
 Идентификатор для тега, который предшествует комментариям.  Заключить его в одинарные или двойные кавычки.  
  
## Заметки  
 Тег \<include\> использует синтаксис XPath XML.  См. документацию XPath для способов настраивать с помощью \<include\>.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## Пример  
 В данном примере используется несколько файлов.  Первый файл, который использует \<include\>содержит следующие комментарии документации:  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 Второй файл — xml\_include\_tag.doc — содержит следующие комментарии к документации.  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## Выходные данные программы  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)