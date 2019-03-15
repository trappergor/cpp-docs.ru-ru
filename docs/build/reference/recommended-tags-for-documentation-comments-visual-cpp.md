---
title: Рекомендуемые теги для комментариев документации (комментариев документации C++)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: adb8440dc07f8f3e193b58be6782859fbb8413e4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827036"
---
# <a name="recommended-tags-for-documentation-comments"></a>Рекомендуемые теги для комментариев документации

Компилятор MSVC будет обрабатывать комментарии к документации в коде и создает XDC-файл для каждой единице компиляции и xdcmake.exe обработает XDC-файлы в XML-файл. Обработка XML-файла для создания документации — это аспект, который нужно реализовать на вашем сайте.

Теги обрабатываются в конструкциях, таких как типы и их члены.

Теги должны стоять прямо перед типами или членами.

> [!NOTE]
>  Комментарии документации невозможно применить к пространству имен или к внешнему определению для свойств и событий; эти комментарии должны находиться в объявлениях внутри класса.

Компилятор обрабатывает любые теги, имеющие допустимый формат XML. С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности:

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<code>](code-visual-cpp.md)|[\<example>](example-visual-cpp.md)|
|[\<exception>](exception-visual-cpp.md)1|[\<include>](include-visual-cpp.md)1|[\<list>](list-visual-cpp.md)|
|[\<para>](para-visual-cpp.md)|[\<param>](param-visual-cpp.md)1|[\<paramref>](paramref-visual-cpp.md)1|
|[\<permission>](permission-visual-cpp.md)1|[\<remarks>](remarks-visual-cpp.md)|[\<returns>](returns-visual-cpp.md)|
|[\<see>](see-visual-cpp.md)1|[\<seealso>](seealso-visual-cpp.md)1|[\<summary>](summary-visual-cpp.md)|
|[\<value>](value-visual-cpp.md)|||

1. Компилятор проверяет синтаксис.

В текущем выпуске компилятор MSVC поддерживает `<paramref>`, тег, который поддерживается другими компиляторами Visual Studio. Возможно, поддержка `<paramref>` будет добавлена в будущих выпусках Visual C++.

## <a name="see-also"></a>См. также

[Документация XML](xml-documentation-visual-cpp.md)