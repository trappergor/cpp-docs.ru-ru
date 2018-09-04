---
title: '&lt;param&gt; (Visual C++) | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- param
- <param>
dev_langs:
- C++
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f8fae2d8af1b7121290bfbd42b2668afc50034c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217257"
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)
Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<param name='name'>description</param>  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра метода.  Заключите имя в одинарные или двойные кавычки.  Если компилятору не удается найти `name`, он выдает предупреждение.  
  
 `description`  
 Описание параметра.  
  
## <a name="remarks"></a>Примечания  
 Текст тега \<param> будет отображаться в IntelliSense, в [обозревателе объектов](https://msdn.microsoft.com/f89acfc5-1152-413d-9f56-3dc16e3f0470) и в веб-отчете комментариев кода.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## <a name="example"></a>Пример  
  
```  
// xml_param_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_param_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <param name="Int1">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)