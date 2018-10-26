---
title: Структура SYSTEMTIME | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6882a4e169b7efa67bef02ab5abee1276384e52f
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334574"
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

