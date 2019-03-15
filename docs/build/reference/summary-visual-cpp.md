---
title: '&lt;Сводка > (C++ комментариев документации)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 68bb8b7c269b3406438e5cf21dde7179f7e67646
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826576"
---
# <a name="ltsummarygt"></a>&lt;summary&gt;

Тег \<summary> следует использовать для описания типа или члена типа. Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](remarks-visual-cpp.md).

## <a name="syntax"></a>Синтаксис

```
<summary>description</summary>
```

#### <a name="parameters"></a>Параметры

*description*<br/>
Сводка объекта.

## <a name="remarks"></a>Примечания

Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense, а также отображается в [обозревателе объектов](/visualstudio/ide/viewing-the-structure-of-code) и веб-отчете комментариев кода.

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

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

[Документация XML](xml-documentation-visual-cpp.md)
