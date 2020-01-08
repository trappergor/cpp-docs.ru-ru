---
title: _TRUNCATE
ms.date: 11/04/2016
f1_keywords:
- _TRUNCATE
- TRUNCATE
helpviewer_keywords:
- TRUNCATE constant
- _TRUNCATE constant
ms.assetid: ad093dbf-1aa5-4bd2-9268-efc68afd8434
ms.openlocfilehash: b472fceffa6284baaaf4dc1780ab54399fdd42c7
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301682"
---
# <a name="_truncate"></a>_TRUNCATE

Определяет поведение усечения строки.

## <a name="syntax"></a>Синтаксис

```
#include <stdlib.h>
```

## <a name="remarks"></a>Заметки

`_TRUNCATE` разрешает усечение, если передается в качестве параметра `count` этим функциям:

[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)

[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)

[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)

[mbsrtowcs_s](../c-runtime-library/reference/mbsrtowcs-s.md)

[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)

[wcsrtombs_s](../c-runtime-library/reference/wcsrtombs-s.md)

[_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)

[vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)

Если буфер назначения слишком мал для хранения всей строки, нормальным поведением для этих функций является интерпретация этой ситуации как ошибки (см. раздел [Проверка параметров](../c-runtime-library/parameter-validation.md)). Однако, если разрешено усечение строки путем передачи `_TRUNCATE`, эти функции копируют столько символов, сколько возможно, завершая буфер нулевым символом, и успешно завершаются.

Усечение строки меняет возвращаемые значения соответствующих функций. Следующие функции возвращают 0, если усечение не происходит, или `STRUNCATE`, если усечение происходит.

[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)

[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)

[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)

[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)

Следующие функции возвращают количество скопированных символов при отсутствии усечения или -1, если усечение не происходит (соответствуя поведению исходных функций snprintf).

[_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)

[vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)

## <a name="example"></a>Пример

```c
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

```Output
truncation occurred!
'1234'
```

## <a name="see-also"></a>См. также:

[Глобальные константы](../c-runtime-library/global-constants.md)
