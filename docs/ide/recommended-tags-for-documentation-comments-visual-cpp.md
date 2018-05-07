---
title: Рекомендуемые теги для комментариев документации (Visual C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b25ad029a59c4b23bcab093b3742f16f7ca9175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Рекомендуемые теги для комментариев документации (Visual C++)
Компилятор Visual C++ будет обрабатывать комментарии в коде и создает XDC-файл для каждого объекта компиляции и xdcmake.exe будет обрабатывать XDC-файлы в XML-файл. Обработка XML-файла для создания документации — детализации, который должен быть реализован на вашем сайте.  
  
 Теги обрабатываются на конструкций, таких как типы и члены типов.  
  
 Теги должен предшествовать типы или члены.  
  
> [!NOTE]
>  Комментарии документации не может применяться к пространству имен или в вне определения свойства и события; для объявления в классе должен комментарии к документации.  
  
 Компилятор обрабатывает любые теги, имеющие допустимый формат XML. Следующие теги предоставляют часто используемые возможности в пользовательской документации:  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<исключение >](../ide/exception-visual-cpp.md)1|[\<включить >](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<PARAM >](../ide/param-visual-cpp.md)1|[\<paramref >](../ide/paramref-visual-cpp.md)1|  
|[\<разрешение >](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<в разделе >](../ide/see-visual-cpp.md)1|[\<seealso >](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. Компилятор проверяет синтаксис.  
  
 В текущей версии компилятора Visual C++ не поддерживает `<paramref>`, тег, который поддерживается других компиляторов Visual Studio. Visual C++ может поддерживать `<paramref>` в будущем выпуске.  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)