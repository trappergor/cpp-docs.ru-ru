---
title: DHtmlUrlEventMapEntry Structure
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c9b58067a9c8b6a71cd22b654a2f82ba0f8bfe36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322739"
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
