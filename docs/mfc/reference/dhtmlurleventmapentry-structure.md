---
title: DHtmlUrlEventMapEntry Structure
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: 0a1dc86080c094a7ac89940cd43a8edac973e10c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431633"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry Structure

`DHtmlUrlEventMapEntry` Структура обеспечивает поддержку сопоставления событий нескольких URL-адресов.

## <a name="syntax"></a>Синтаксис

```
struct DHtmlUrlEventMapEntry
{
LPCTSTR szUrl;
const DHtmlEventMapEntry *pEventMap;
};
```

#### <a name="parameters"></a>Параметры

*szUrl*<br/>
URL-адрес.

*pEventMap*<br/>
Схема событий, связанных с URL-адрес.

## <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

