---
title: "&lt;summary&gt; (Visual C++) | Microsoft Docs"
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
  - "<summary>"
  - "summary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<summary> - XML-тег C++"
  - "summary - XML-тег C++"
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;summary&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<summary\> следует использовать для описания типа или члена типа.  Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks\>](../ide/remarks-visual-cpp.md).  
  
## Синтаксис  
  
```  
<summary>description</summary>  
```  
  
#### Параметры  
 `description`  
 Сводка объекта.  
  
## Заметки  
 Текст для тега \<summary\> единственный источник информации о типе в IntelliSense, а также см. в разделе [Обозреватель объектов](http://msdn.microsoft.com/ru-ru/f89acfc5-1152-413d-9f56-3dc16e3f0470) и в веб\-отчет комментариев кода.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## Пример  
  
```  
// xml_summary_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_summary_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>  
   /// <seealso cref="MyClass::MyMethod2"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void MyMethod2() {}  
};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)