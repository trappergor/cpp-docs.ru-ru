---
title: _controlfp_s
ms.date: 04/05/2018
apiname:
- _controlfp_s
apilocation:
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 0624cbfb4870ca87efebac01a8de682b588a4ca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335390"
---
# <a name="controlfps"></a>_controlfp_s

Возвращает и задает управляющее слово блока операций с плавающей запятой. Это версия функции [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Параметры

*currentControl*<br/>
Значения битов в текущем управляющем слове.

*newControl*<br/>
Значения битов в новом управляющем слове.

*Маска*<br/>
Маска для установки битов нового управляющего слова.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успешного выполнения, или **errno** значение кода ошибки.

## <a name="remarks"></a>Примечания

**_Controlfp_s** функция представляет собой независимый от платформы и безопаснее версию **_control87**, которая получает управляющее слово в адрес, который хранится в  *currentControl* и задает его с помощью *newControl*. Биты в значениях показывают состояние элемента управления блоком операций с плавающей запятой. Состояние элемента управления блока операций с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой в зависимости от платформы. Можно также использовать **_controlfp_s** для маскирования и снять маску исключения с плавающей запятой.

Если значение для *маска* равно 0, **_controlfp_s** получает управляющее слово и сохраняет полученное значение в *currentControl*.

Если *маска* имеет ненулевое значение, устанавливается новое значение управляющего слова: Для любой бит, который имеет значение (то есть равного 1) в *маска*, соответствующий бит в *новый* используется для обновления управляющего слова. Другими словами *fpcntrl* = ((*fpcntrl* & ~*маска*) &#124; (*newControl* & *маски* )) где *fpcntrl* — это слово с плавающей запятой. В этом случае *currentControl* присваивается значение после завершения изменения; это не старое битовое значение управляющего слова.

> [!NOTE]
> По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .

**_controlfp_s** почти идентичен **_control87** функции для Intel (x86), x64 и на платформах ARM. Если вы ориентируетесь x86, x64 или платформы ARM, можно использовать **_control87** или **_controlfp_s**.

Разница между **_control87** и **_controlfp_s** в способе обработки нестандартные значения. Для Intel (x86), x 64 и ARM платформ **_control87** может устанавливать и очищать маску исключения DENORMAL OPERAND. **_controlfp_s** не изменяет маску исключения DENORMAL OPERAND. В следующем примере показано это различие.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Возможные значения константы маски (*маска*) и новые управляющие значения (*newControl*) показаны в следующей таблице шестнадцатеричных значений. Используйте перечисленные ниже переносимые константы (**_MCW_EM**, **_EM_INVALID**, и так далее) в аргументах этих функций вместо явных шестнадцатеричных значений.

Платформы на основе Intel (x86) аппаратно поддерживают входные и выходные значения DENORMAL. В случае x86 значения DENORMAL сохраняются. Платформа ARM и x64 поддерживаемых платформ, SSE2 включить DENORMAL операндов и результатов, чтобы быть записаны на диск или принудительно до нуля. **_Controlfp_s**, **_controlfp**, и **_control87** функции предоставляют маску для изменения этого поведения. В следующем примере показано использование этой маски:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

На платформах ARM **_controlfp_s** функция применяется к регистру fpscr. В x64 архитектур, только управляющее слово SSE2, хранящийся в регистре MXCSR затрагивается регистра. На платформах Intel (x86) **_controlfp_s** влияет на управляющие слова как для x87, так и для SSE2, если он имеется. Возможно два управляющих слова могут быть согласованы друг с другом (из-за предыдущего вызова [__control87_2](control87-controlfp-control87-2.md), например); Если имеется несоответствие между двумя управляющими словами **_controlfp_s** задает **EM_AMBIGUOUS** флаг в *currentControl*. Это предупреждение о том, что возвращенное управляющее слово может неточно представлять состояние обоих управляющих слов блоков операций с плавающей запятой.

В ARM и x64 архитектур, изменение режима бесконечности или точности с плавающей запятой не поддерживается. Если маска управления точностью используется в x64 платформы, функция создает утверждение и вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md).

Если маска задана неправильно, эта функция создает исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **EINVAL** и задает **errno** для **EINVAL**.

Эта функция учитывается при использовании [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) компиляции, поскольку среда CLR (CLR) поддерживает только точность чисел с плавающей запятой по умолчанию.

### <a name="mask-constants-and-values"></a>Константы маски и значения

Для **_MCW_EM** маски, очисткой задает исключение, которое допускает аппаратное исключение; Установка маски скрывает исключение. Если **_EM_UNDERFLOW** или **_EM_OVERFLOW** возникает исключение оборудования не создается до выполнения следующей инструкции с плавающей запятой. Чтобы аппаратное исключение сразу после **_EM_UNDERFLOW** или **_EM_OVERFLOW**, вызвать инструкцию FWAIT MASM.

|Маска|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Управление денормализацией)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (маска исключения прерывания)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (Управление бесконечностью)<br /><br /> (Не поддерживается на ARM или x64 платформ.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Управление округлением)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Управление точностью)<br /><br /> (Не поддерживается на ARM или x64 платформ.)|0x00030000|**_PC_24** (24 бита)<br /><br /> **_PC_53** (53 бита)<br /><br /> **_PC_64** (64 бита)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_contrlfp_s.c
// processor: x86
// This program uses _controlfp_s to output the FP control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word;
    int err;

    // Show original FP control word and do calculation.
    err = _controlfp_s(&control_word, 0, 0);
    if ( err ) /* handle error here */;

    printf( "Original: 0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "24-bit:   0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "Default:  0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x9001f
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0xa001f
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x9001f
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
