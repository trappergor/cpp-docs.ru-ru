---
title: _controlfp_s
ms.date: 4/2/2020
api_name:
- _controlfp_s
- _o__controlfp_s
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 4b36cc9f5ed83b68cb15c39be91165ed7aa86d7b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348533"
---
# <a name="_controlfp_s"></a>_controlfp_s

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

*текущийКонтроль*<br/>
Значения битов в текущем управляющем слове.

*newControl*<br/>
Значения битов в новом управляющем слове.

*маска*<br/>
Маска для установки битов нового управляющего слова.

## <a name="return-value"></a>Возвращаемое значение

Нулевой, если успешно, или код ошибки **значения errno.**

## <a name="remarks"></a>Remarks

Функция **_controlfp_s** является независимая от платформы и более безопасная версия **_control87,** которая получает слово управления плавающей точкой в адрес, который хранится в *currentControl* и устанавливает его с помощью *newControl.* Биты в значениях показывают состояние элемента управления блоком операций с плавающей запятой. Состояние элемента управления блока операций с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой в зависимости от платформы. Вы также можете использовать **_controlfp_s** для маскировки или разоблачения исключений из плавающей точки.

Если значение *маски* равно 0, **_controlfp_s** получает слово управления плавающей точкой и хранит извлеченное значение в *currentControl.*

Если *маска* незеро, устанавливается новое значение для контрольного слова: для любого набора бита (т.е. равного 1) в *маске,* соответствующий бит в *новом* используется для обновления контрольного слова. Другими словами, *fpcntrl* ((fpcntrl &*маски)*&#124;*(маска newControl)),* & *mask*где *fpcntrl* является плавающим словом управления точки.*fpcntrl* В этом сценарии *currentControl* устанавливается к значению после завершения изменения; это не старое значение бита контрольного слова.

> [!NOTE]
> По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .

**_controlfp_s** практически идентичен **функции _control87** на платформах Intel (x86), x64 и ARM. Если вы ориентируетесь на платформы x86, x64 или ARM, вы можете использовать **_control87** или **_controlfp_s.**

Разница между **_control87** и **_controlfp_s** заключается в том, как они относятся к денормальным значениям. Для платформ Intel (x86), x64 и ARM **_control87** могут установить и очистить маску исключения DENORMAL OPERAND. **_controlfp_s** не изменяет маску исключения DENORMAL OPERAND. В следующем примере показано это различие.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Возможные значения для константы маски *(маска)* и новые значения управления *(newControl)* отображаются в следующей таблице hexadecimal Values. Используйте портативные константы, перечисленные ниже **(_MCW_EM,** **_EM_INVALID**и так далее) в качестве аргументов для этих функций, а не поставлять гексадецимальные значения явно.

Платформы на основе Intel (x86) аппаратно поддерживают входные и выходные значения DENORMAL. В случае x86 значения DENORMAL сохраняются. Платформа ARM и платформы x64, которые имеют поддержку SSE2, позволяют промыть или свернуть результаты DENORMAL или свести их к нулю. **Функции _controlfp_s,** **_controlfp**и **_control87** обеспечивают маску для изменения такого поведения. В следующем примере показано использование этой маски:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

На платформах ARM функция **_controlfp_s** применяется к регистру FPSCR. На архитектурах x64 влияет только контрольное слово SSE2, хранящееся в регистре MXCSR. На платформах Intel (x86) **_controlfp_s** влияет на слова управления как для x87, так и для SSE2, если они присутствуют. Это возможно для двух контрольных слов, чтобы быть несовместимыми друг с другом (из-за предыдущего вызова [__control87_2,](control87-controlfp-control87-2.md)например); если есть несоответствие между двумя контрольными словами, **_controlfp_s** устанавливает **EM_AMBIGUOUS** флаг в *currentControl.* Это предупреждение о том, что возвращенное управляющее слово может неточно представлять состояние обоих управляющих слов блоков операций с плавающей запятой.

На архитектурах ARM и x64 изменение режима бесконечности или точность плавающей точки не поддерживается. Если на платформе x64 используется маска точного управления, функция повышает утверждение и вызывается недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md)

Если маска задана неправильно, эта функция создает исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эта функция возвращает **EINVAL** и устанавливает **errno** **в EINVAL.**

Эта функция игнорируется при использовании [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) для компиляции, поскольку общее время выполнения языка (CLR) поддерживает точность плавающей точки по умолчанию.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="mask-constants-and-values"></a>Маска константы и ценности

Для **_MCW_EM** маски очистка устанавливает исключение, которое позволяет исключение оборудования; настройка этого скрывают исключение. При **возникновении _EM_UNDERFLOW** или **_EM_OVERFLOW** не будет исключений из аппаратного обеспечения до выполнения следующей инструкции плавающей точки. Чтобы создать аппаратное исключение сразу после **_EM_UNDERFLOW** или **_EM_OVERFLOW,** позвоните в инструкцию FWAIT MASM.

|Mask|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Денормальный контроль)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Маска исключения прерывания)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (Управление бесконечностью)<br /><br /> (Не поддерживается на платформах ARM или x64.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Управление округлением)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Точное управление)<br /><br /> (Не поддерживается на платформах ARM или x64.)|0x00030000|**_PC_24** (24 бита)<br /><br /> **_PC_53** (53 бита)<br /><br /> **_PC_64** (64 бита)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
