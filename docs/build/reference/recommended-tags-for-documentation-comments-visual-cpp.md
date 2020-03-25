---
title: Рекомендуемые теги для комментариев документации (C++ комментарии к документации)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 4e0937b79012f65ba136e18ac81f014be23688f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168867"
---
# <a name="recommended-tags-for-documentation-comments"></a>Рекомендуемые теги для комментариев документации

Компилятор КОМПИЛЯТОРОМ MSVC будет обрабатывать комментарии к документации в коде и создает XDC-файл для каждого компилируемого объекта, а Программа xdcmake. exe будет обрабатывать XDC-файлы в формате XML. Обработка XML-файла для создания документации — это аспект, который нужно реализовать на вашем сайте.

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

В текущем выпуске компилятор КОМПИЛЯТОРОМ MSVC не поддерживает `<paramref>`, тег, который поддерживается другими компиляторами Visual Studio. Возможно, поддержка `<paramref>` будет добавлена в будущих выпусках Visual C++.

## <a name="see-also"></a>См. также раздел

[Документация XML](xml-documentation-visual-cpp.md)
