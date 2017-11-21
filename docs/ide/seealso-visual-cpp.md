---
title: "&lt;seealso&gt; (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <seealso>
- seealso
dev_langs: C++
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bd43a5252481a8b21220dac14248ac5ae9f01d09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltseealsogt-visual-c"></a>&lt;seealso&gt; (Visual C++)
Кроме того, с помощью тега \<seealso> можно указать текст, который должен отображаться в разделе "См. также". Тег [\<see>](../ide/see-visual-cpp.md) позволяет задать ссылку из текста.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Параметры  
 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.  Заключите имя в одинарные или двойные кавычки.  
  
 Компилятор проверяет, что данный элемент кода существует и устраняет `member` имени элемента в выходных данных XML.  Если компилятору не удается найти `member`, он выдает предупреждение.  
  
 Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../ide/see-visual-cpp.md).  
  
## <a name="remarks"></a>Примечания  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
 В разделе [\<summary>](../ide/summary-visual-cpp.md) можно найти пример использования тега \<seealso>.  
  
 Компилятор Visual C++ будет пытаться разрешить ссылки cref за один проход по комментариям документации.  Поэтому если при использовании правил поиска C++ компилятор не найдет символ, ссылка будет помечена как не разрешенная.  
  
## <a name="example"></a>Пример  
 В следующем примере в cref упоминается неразрешенный символ. XML-комментарий для cref для B::Test будет `<seealso cref="!:B::Test" />`, тогда как ссылка на A::Test является корректным `<seealso cref="M:A.Test" />`.  
  
```  
// xml_seealso_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_seealso_tag.dll  
  
/// Text for class A.  
public ref struct A {  
   /// <summary><seealso cref="A::Test"/>  
   /// <seealso cref="B::Test"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void Test() {}  
};  
  
/// Text for class B.  
public ref struct B {  
   void Test() {}  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)