---
title: Структура DHtmlUrlEventMapEntry | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbac4b372f06f288eede8c578372d45334a5d707
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427528"
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

