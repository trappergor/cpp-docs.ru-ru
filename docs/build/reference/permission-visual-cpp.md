---
title: '&lt;разрешение > (C++ комментариев документации)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: 764048f7bc579afa6862bdff40968588955dc307
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826996"
---
# <a name="ltpermissiongt"></a>&lt;Разрешение&gt;

Тег \<permission> tag позволяет документировать уровень доступа для члена. <xref:System.Security.PermissionSet> позволяет задать уровень доступа для члена.

## <a name="syntax"></a>Синтаксис

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>Параметры

*member*<br/>
Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.  Заключите имя в одинарные или двойные кавычки.

Если компилятору не удается найти `member`, он выдает предупреждение.

Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](see-visual-cpp.md).

*description*<br/>
Описание уровня доступа для члена.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

Компилятор MSVC будет пытаться разрешить ссылки cref за один проход комментарии к документации.  Поэтому если при использовании правил поиска C++ компилятор не найдет символ, ссылка будет помечена как не разрешенная. Дополнительные сведения см. в описании [\<seealso>](seealso-visual-cpp.md).

## <a name="example"></a>Пример

```
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>См. также

[Документация XML](xml-documentation-visual-cpp.md)
