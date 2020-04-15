---
title: Рекомендуемые теги для комментариев к документации (комментарии к документации КЗ)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 1648d0eb019a3aad25641d7f6a7edd1ba26acf7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336175"
---
# <a name="recommended-tags-for-documentation-comments"></a>Рекомендуемые теги для комментариев документации

Компилятор MSVC будет обрабатывать комментарии документации в вашем коде и создает файл .xdc для каждого сборника, а xdcmake.exe будет обрабатывать файлы .xdc в файл .xml. Обработка XML-файла для создания документации — это аспект, который нужно реализовать на вашем сайте.

Теги обрабатываются в конструкциях, таких как типы и их члены.

Теги должны стоять прямо перед типами или членами.

> [!NOTE]
> Комментарии документации невозможно применить к пространству имен или к внешнему определению для свойств и событий; эти комментарии должны находиться в объявлениях внутри класса.

Компилятор обрабатывает любые теги, имеющие допустимый формат XML. С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности:

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<код>](code-visual-cpp.md)|[\<пример>](example-visual-cpp.md)|
|исключение>1 [ \< ](exception-visual-cpp.md)|включают>1 [ \< ](include-visual-cpp.md)|[\<список>](list-visual-cpp.md)|
|[\<пара>](para-visual-cpp.md)|пара>1 [ \< ](param-visual-cpp.md)|парамреф>1 [ \< ](paramref-visual-cpp.md)|
|разрешение>1 [ \< ](permission-visual-cpp.md)|[\<замечания>](remarks-visual-cpp.md)|[\<возвращает>](returns-visual-cpp.md)|
|см>1 [ \< ](see-visual-cpp.md)|seealso>1 [ \< ](seealso-visual-cpp.md)|[\<резюме>](summary-visual-cpp.md)|
|[\<значение>](value-visual-cpp.md)|||

1. Компилятор проверяет синтаксис.

В текущем выпуске компилятор MSVC не поддерживает `<paramref>`тег, поддерживаемый другими компиляторами Visual Studio. Возможно, поддержка `<paramref>` будет добавлена в будущих выпусках Visual C++.

## <a name="see-also"></a>См. также раздел

[Документация XML](xml-documentation-visual-cpp.md)
