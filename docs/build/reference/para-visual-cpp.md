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
ms.openlocfilehash: d8de55344eef7634d8a9a55a32b8ff5beb8852d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320023"
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