---
title: "_TRUNCATE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_TRUNCATE"
  - "TRUNCATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_TRUNCATE - константа"
  - "TRUNCATE - константа"
ms.assetid: ad093dbf-1aa5-4bd2-9268-efc68afd8434
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _TRUNCATE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет поведение усечения строки.  
  
## Синтаксис  
  
```  
#include <stdlib.h>  
```  
  
## Заметки  
 `_TRUNCATE` разрешает усечение, если передается в качестве параметра `count` этим функциям:  
  
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)  
  
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 [mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)  
  
 [wcstombs\_s, \_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)  
  
 [wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)  
  
 [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
 Если буфер назначения слишком мал для хранения всей строки, нормальным поведением для этих функций является интерпретирование этой ситуации как ошибки \(см. раздел [Проверка параметров](../c-runtime-library/parameter-validation.md)\).  Однако если разрешено усечение строки путем передачи `_TRUNCATE`, эти функции копируют столько символов, сколько возможно, завершая буфер нулевым символом, и успешно завершаются.  
  
 Усечение строки меняет возвращаемые значения соответствующих функций.  Следующие функции возвращают 0, если не происходит усечение, или `STRUNCATE`, если происходит усечение.  
  
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)  
  
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [wcstombs\_s, \_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)  
  
 [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 Следующие функции возвращают количество копированных символов при отсутствии усечения или \-1, если происходит усечение \(соответствуя поведению исходных функций snprintf\).  
  
 [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
## Пример  
  
```  
// crt_truncate.c  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
   char src[] = "1234567890";  
   char dst[5];  
   errno_t err = strncpy_s(dst, _countof(dst), src, _TRUNCATE);  
   if ( err == STRUNCATE )  
      printf( "truncation occurred!\n" );  
   printf( "'%s'\n", dst );  
}  
```  
  
  **truncation occurred\!**  
**'1234'**   
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)