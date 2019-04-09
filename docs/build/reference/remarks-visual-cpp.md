---
title: '&lt;Примечания > (C++ комментариев документации)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 0d0c63d55de80f498498a6873dacb5e83fc956b7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827176"
---
# <a name="ltremarksgt"></a>&lt;remarks&gt;

Тег \<remarks> позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](summary-visual-cpp.md). Эта информация отображается в [обозревателе объектов](/visualstudio/ide/viewing-the-structure-of-code) и в веб-отчете комментариев кода.

## <a name="syntax"></a>Синтаксис

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>Параметры

*description*<br/>
Описание элемента.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

```
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>См. также

[Документация XML](xml-documentation-visual-cpp.md)
