---
title: Структура SYSTEMTIME
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
ms.openlocfilehash: b46482a9f4eb0165b72d74cb7d69e96e2a15e953
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559068"
---
# <a name="systemtime-structure"></a>Структура SYSTEMTIME

`SYSTEMTIME` Структура представляет дату и время, с использованием отдельных элементов для месяца, дня, года, дня недели, часа, минуты, секунды и миллисекунды.

## <a name="syntax"></a>Синтаксис

```
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME;
```

#### <a name="parameters"></a>Параметры

*wYear*<br/>
Текущий год.

*wMonth*<br/>
Текущий месяц; Январь — 1.

*wDayOfWeek*<br/>
Текущий день недели. 0 — воскресенье, понедельник = 1 и т. д.

*поля wDay*<br/>
Текущий день месяца.

*wHour*<br/>
Текущий час.

*wMinute*<br/>
Текущая минута.

*wSecond*<br/>
Текущая секунда.

*wMilliseconds*<br/>
Текущая миллисекунда.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** winbase.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

