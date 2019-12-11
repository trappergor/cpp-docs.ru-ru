---
title: '&lt;возвращает > (C++ комментарии к документации)'
ms.date: 11/04/2016
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: 1315ec09271c2c97f7bcaf3fb6f9c75f514b5d2d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988630"
---
# <a name="ltreturnsgt"></a>&lt;returns&gt;

Тег \<returns> следует использовать в комментариях к объявлению метода для описания возвращаемого значения.

## <a name="syntax"></a>Синтаксис

```
<returns>description</returns>
```

#### <a name="parameters"></a>Параметры

*description*<br/>
Описание возвращаемого значения.

## <a name="remarks"></a>Заметки

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

```cpp
// xml_returns_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_returns_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <returns>Returns zero.</returns>
   int GetZero() { return 0; }
};
```

## <a name="see-also"></a>См. также:

[Документация XML](xml-documentation-visual-cpp.md)
