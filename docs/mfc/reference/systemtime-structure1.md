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
- SYSTEMTIME structure
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 298b2673a3eb05525683f8269fcd415d5be1c80a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
`SYSTEMTIME` Структура представляет дату и время, с использованием отдельных элементов для месяц, день, год, день недели, час, минуты, секунды и миллисекунды.  
  
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
 Текущий день недели; 0 — воскресенье, понедельник — 1 и т. д.  
  
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
 [!code-cpp[NVC_MFC_Utilities&#39;](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)


