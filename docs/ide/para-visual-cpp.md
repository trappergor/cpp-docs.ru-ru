---
title: '&lt;para&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C++ XML tag
- para C++ XML tag
ms.assetid: 35f2a1b3-bc14-4f13-bcb0-c39ccbf74d59
ms.openlocfilehash: d08893b338ae2dcab1c9423e6d88828b8fd74ee5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740909"
---
# <a name="ltparagt-visual-c"></a>&lt;para&gt; (Visual C++)

Тег \<para> используется внутри другого тега, например [\<summary>](../ide/summary-visual-cpp.md), [\<remarks>](../ide/remarks-visual-cpp.md) или [\<returns>](../ide/returns-visual-cpp.md), и позволяет добавить к тексту структуру.

## <a name="syntax"></a>Синтаксис

```
<para>content</para>
```

#### <a name="parameters"></a>Параметры

*content*<br/>
Текст абзаца.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

В разделе [\<summary>](../ide/summary-visual-cpp.md) можно найти пример использования тега \<para>.

## <a name="see-also"></a>См. также

[Документация XML](../ide/xml-documentation-visual-cpp.md)
