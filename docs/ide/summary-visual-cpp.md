---
title: '&lt;summary&gt; (Visual C++) | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <summary>
- summary
dev_langs:
- C++
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0dff1d6ce31f6b26c0f8a46ef2ff620a4d40f93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322293"
---
# <a name="ltsummarygt-visual-c"></a>&lt;summary&gt; (Visual C++)
Тег \<summary> следует использовать для описания типа или члена типа. Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../ide/remarks-visual-cpp.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Сводка объекта.  
  
## <a name="remarks"></a>Примечания  
 Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense, а также отображается в [обозревателе объектов](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) и веб-отчете комментариев кода.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)