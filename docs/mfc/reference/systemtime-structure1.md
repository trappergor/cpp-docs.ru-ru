---
title: SYSTEMTIME Structure1 | Документы Microsoft
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
ms.openlocfilehash: 97a0042adaa223fc5898c057f191f7b750fa230f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372396"
---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
`SYSTEMTIME` Структура представляет дату и время, с использованием отдельных элементов для месяц, день, год, дня недели, час, минуты, секунды и миллисекунды.  
  
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
 *wYear*  
 Текущий год.  
  
 *wMonth*  
 Текущий месяц; Январь — 1.  
  
 *wDayOfWeek*  
 Текущий день недели; 0 — воскресенье, понедельник, 1 и т. д.  
  
 *поля wDay*  
 Текущий день месяца.  
  
 *wHour*  
 Текущий час.  
  
 *wMinute*  
 Текущую минуту.  
  
 *wSecond*  
 Текущая секунда.  
  
 *wMilliseconds*  
 Текущей миллисекунды.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

