---
title: hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl
description: Справочник по API для hypot, хипотф, хипотл, _hypot, _hypotf и _hypotl; который вычисляет гипотенузу.
ms.date: 9/1/2020
api_name:
- _hypotf
- hypot
- hypotf
- _hypot
- _hypotl
- hypotl
- _o__hypot
- _o__hypotf
- _o_hypot
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- hypotf
- hypotl
- _hypotl
- hypot
- _hypot
- _hypotf
helpviewer_keywords:
- hypotenuse calculation
- hypot function
- hypotf function
- triangles, calculating hypotenuse
- hypotl function
- calculating hypotenuses
- _hypot function
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
ms.openlocfilehash: 199e330dcd78c372a0279cac9f0e96cb47c561e8
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556454"
---
# <a name="hypot-hypotf-hypotl-_hypot-_hypotf-_hypotl"></a>hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl

Вычисляет гипотенузу.

## <a name="syntax"></a>Синтаксис

```C
double hypot(
   double x,
   double y
);
float hypotf(
   float x,
   float y
);
long double hypotl(
   long double x,
   long double y
);
double _hypot(
   double x,
   double y
);
float _hypotf(
   float x,
   float y
);
long double _hypotl(
   long double x,
   long double y
);
#define hypotf(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*, *y*\
Значения с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **hypot** возвращает длину гипотенузы; в случае переполнения **hypot** возвращает INF-файл (бесконечность **), а для переменной возврата** — значение **ERANGE**. Для изменения обработки ошибок можно использовать **_matherr** .

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функции **hypot** вычисляют длину гипотенузы правого треугольника, учитывая длину двух сторон *x* и *y* (иными словами, квадратный корень из *x*<sup>2</sup>  +  *y*<sup>2</sup>).

Для совместимости с более ранними стандартами используются версии функций с символом подчеркивания в начале. Их поведение идентично поведению версий, которые не имеют таких символов. В новом коде рекомендуется использовать версии без символов подчеркивания.

При использовании \<tgmath.h> `hypot()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**hypot**, **хипотф**, **хипотл**, **_hypot**, **_hypotf**, **_hypotl**|\<math.h>|
|макрос **hypot** | \<tgmath.h> |

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_hypot.c
// This program prints the hypotenuse of a right triangle.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 3.0, y = 4.0;

   printf( "If a right triangle has sides %2.1f and %2.1f, "
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );
}
```

```Output
If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[_matherr](matherr.md)<br/>
