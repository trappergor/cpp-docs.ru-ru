---
title: Рекомендуемые теги для комментариев документации (комментарии к документации по C++)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 9f41e450215e2bce02dbaf66910fc2fc1a131a99
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836859"
---
# <a name="recommended-tags-for-documentation-comments"></a>Рекомендуемые теги для комментариев документации

Компилятор КОМПИЛЯТОРОМ MSVC будет обрабатывать комментарии к документации в коде и создает XDC-файл для каждого компилируемого объекта, а xdcmake.exe будет обрабатывать XDC-файлы в файл. XML. Обработка XML-файла для создания документации — это аспект, который нужно реализовать на вашем сайте.

Теги обрабатываются в конструкциях, таких как типы и их члены.

Теги должны стоять прямо перед типами или членами.

> [!NOTE]
> Комментарии документации невозможно применить к пространству имен или к внешнему определению для свойств и событий; эти комментарии должны находиться в объявлениях внутри класса.

Компилятор обрабатывает любые теги, имеющие допустимый формат XML. С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности:

[`<c>`](c-visual-cpp.md)
[`<code>`](code-visual-cpp.md)
[`<example>`](example-visual-cpp.md)
[`<exception>`](exception-visual-cpp.md)<sup>1</sup> 
 1 [`<include>`](include-visual-cpp.md) <sup>1</sup> 
 [`<list>`](list-visual-cpp.md) 1 
 [`<para>`](para-visual-cpp.md) 
 [`<param>`](param-visual-cpp.md) <sup>1</sup> 
 1 [`<paramref>`](paramref-visual-cpp.md) <sup>1</sup> 
 1 [`<permission>`](permission-visual-cpp.md) <sup>1</sup> 
 [`<remarks>`](remarks-visual-cpp.md) 1 
 [`<returns>`](returns-visual-cpp.md) 
 [`<see>`](see-visual-cpp.md) <sup>1</sup> 
 1 [`<seealso>`](seealso-visual-cpp.md) <sup>1</sup>
[`<summary>`](summary-visual-cpp.md)
[`<value>`](value-visual-cpp.md)

1. Компилятор проверяет синтаксис.

В текущем выпуске компилятор КОМПИЛЯТОРОМ MSVC не поддерживает тег, `<paramref>` который поддерживается другими компиляторами Visual Studio. Возможно, поддержка `<paramref>` будет добавлена в будущих выпусках Visual C++.

## <a name="see-also"></a>См. также раздел

[Документация XML](xml-documentation-visual-cpp.md)
