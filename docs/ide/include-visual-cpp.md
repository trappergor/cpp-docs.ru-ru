---
title: "&lt;включить&gt; (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9a6b07ce540d67a44e46a24fb943dac93bb95a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ltincludegt-visual-c"></a>&lt;включить&gt; (Visual C++)
Тег \<include> позволяет задать ссылку на комментарии в другом файле, которые описывают типы и члены вашего исходного кода. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  Например, можно использовать \<включают > Вставить стандартные «стандартный» комментарии, которые используются в команде или организации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути.  Заключите имя в одинарные или двойные кавычки.  Если компилятору не удается найти `filename`, он выдает предупреждение.  
  
 `tagpath`  
 Допустимое выражение XPath, выбирает нужный узел набора, содержащиеся в файле.  
  
 `name`  
 Спецификатор имени в теге, предшествующий комментариям. `name` будет иметь идентификатор `id`.  
  
 `id`  
 Идентификатор тега, который предшествует комментариям.  Заключите имя в одинарные или двойные кавычки.  
  
## <a name="remarks"></a>Примечания  
 Тег \<include> использует XML-синтаксис XPath. XPath документации о способах настройки с помощью \<включают >.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## <a name="example"></a>Пример  
 В этом примере представлено несколько файлов. Первый файл, который использует \<включают >, содержит следующие комментарии к документации:  
  
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
  
 Второй файл (xml_include_tag.doc) содержит следующие комментарии документации:  
  
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
  
## <a name="program-output"></a>Выходные данные программы  
  
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
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)