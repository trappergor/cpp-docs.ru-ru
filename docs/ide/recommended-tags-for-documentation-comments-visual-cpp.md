---
title: Рекомендуемые теги для комментариев документации (Visual C++)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 251baedbf37901a58b34b66b7a10bbdcf5d66557
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564194"
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Рекомендуемые теги для комментариев документации (Visual C++)

Компилятор Visual C++ обрабатывает комментарии документации в коде и создает XDC-файл для каждой единицы компиляции, а xdcmake.exe преобразует XDC-файлы в XML-файл. Обработка XML-файла для создания документации — это аспект, который нужно реализовать на вашем сайте.

Теги обрабатываются в конструкциях, таких как типы и их члены.

Теги должны стоять прямо перед типами или членами.

> [!NOTE]
>  Комментарии документации невозможно применить к пространству имен или к внешнему определению для свойств и событий; эти комментарии должны находиться в объявлениях внутри класса.

Компилятор обрабатывает любые теги, имеющие допустимый формат XML. С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности:

||||
|-|-|-|
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|
|[\<exception>](../ide/exception-visual-cpp.md)1|[\<include>](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|
|[\<para>](../ide/para-visual-cpp.md)|[\<param>](../ide/param-visual-cpp.md)1|[\<paramref>](../ide/paramref-visual-cpp.md)1|
|[\<permission>](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|
|[\<see>](../ide/see-visual-cpp.md)1|[\<seealso>](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|
|[\<value>](../ide/value-visual-cpp.md)|||

1. Компилятор проверяет синтаксис.

В текущем выпуске компилятор Visual C++ не поддерживает тег`<paramref>`, который поддерживают другие компиляторы Visual Studio. Возможно, поддержка `<paramref>` будет добавлена в будущих выпусках Visual C++.

## <a name="see-also"></a>См. также

[Документация XML](../ide/xml-documentation-visual-cpp.md)