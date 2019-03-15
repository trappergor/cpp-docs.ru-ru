---
title: '&lt;включить > (C++ комментариев документации)'
ms.date: 11/04/2016
f1_keywords:
- include
- <include>
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
ms.openlocfilehash: b7d1033aa5b6c95c0db8eb9debf74596dc214fb0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827386"
---
# <a name="ltincludegt"></a>&lt;include&gt;

Тег \<include> позволяет задать ссылку на комментарии в другом файле, которые описывают типы и члены вашего исходного кода. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  Например, можно использовать \<include> для вставки стандартных комментариев, которые применяются в вашей команде или организации.

## <a name="syntax"></a>Синтаксис

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>Параметры

*filename*<br/>
Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути.  Заключите имя в одинарные или двойные кавычки.  Если компилятору не удается найти `filename`, он выдает предупреждение.

*tagpath*<br/>
Допустимое выражение XPath, которое выбирает нужный набор узлов, содержащийся в файле.

*name*<br/>
Спецификатор имени в теге, предшествующий комментариям. `name` будет иметь идентификатор `id`.

*id*<br/>
Идентификатор тега, который предшествует комментариям.  Заключите имя в одинарные или двойные кавычки.

## <a name="remarks"></a>Примечания

Тег \<include> использует XML-синтаксис XPath. Сведения об использовании тега \<include>. см. в документации по XPath.

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

В этом примере представлено несколько файлов. Первый файл, использующий \<include>, содержит следующие комментарии документации:

```cpp
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

```xml
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

```xml
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

[Документация XML](xml-documentation-visual-cpp.md)
