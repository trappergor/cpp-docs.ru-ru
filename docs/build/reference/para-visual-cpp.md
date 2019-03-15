---
title: '&lt;para>'
ms.date: 11/04/2016
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C++ XML tag
- para C++ XML tag
ms.assetid: 35f2a1b3-bc14-4f13-bcb0-c39ccbf74d59
ms.openlocfilehash: e7cb997d18a778bca3efd4552f543ec5401e8dd0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826673"
---
# <a name="ltparagt"></a>&lt;para&gt;

Тег \<para> используется внутри другого тега, например [\<summary>](summary-visual-cpp.md), [\<remarks>](remarks-visual-cpp.md) или [\<returns>](returns-visual-cpp.md), и позволяет добавить к тексту структуру.

## <a name="syntax"></a>Синтаксис

```
<para>content</para>
```

#### <a name="parameters"></a>Параметры

*content*<br/>
Текст абзаца.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

В разделе [\<summary>](summary-visual-cpp.md) можно найти пример использования тега \<para>.

## <a name="see-also"></a>См. также

[Документация XML](xml-documentation-visual-cpp.md)