---
title: "SYSTEMTIME Structure1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07af222a3d51ff1cc71076d5bbcc3513a3d6cad4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

