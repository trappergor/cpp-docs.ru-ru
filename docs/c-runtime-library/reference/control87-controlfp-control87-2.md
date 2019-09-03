---
title: _control87, _controlfp, __control87_2
ms.date: 08/29/2019
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
ms.openlocfilehash: 75b2870543ec3ddd20d445a492ad4270b91e80d7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218414"
---
# <a name="_control87-_controlfp-__control87_2"></a>_control87, _controlfp, __control87_2

Возвращает и задает управляющее слово блока операций с плавающей запятой. Доступна более безопасная версия **_controlfp** . см. [_controlfp_s](controlfp-s.md).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _control87(
   unsigned int new,
   unsigned int mask
);
unsigned int _controlfp(
   unsigned int new,
   unsigned int mask
);
int __control87_2(
   unsigned int new,
   unsigned int mask,
   unsigned int* x86_cw,
   unsigned int* sse2_cw
);
```

### <a name="parameters"></a>Параметры

*new*\
Значения битов в новом управляющем слове.

*виде*\
Маска для установки битов нового управляющего слова.

*x86_cw*\
Заполняется управляющим словом для блока операций с плавающей запятой x87. Передайте значение 0 (**null**), чтобы задать только управляющее слово SSE2.

*sse2_cw*\
Управляющее слово для блока операций с плавающей запятой SSE. Передайте значение 0 (**null**), чтобы задать только управляющее слово x87.

## <a name="return-value"></a>Возвращаемое значение

Для **_control87** и **_controlfp**биты в возвращаемом значении указывают на состояние элемента управления с плавающей запятой. Полное определение битов, возвращаемых функцией **_control87**, см. в разделе float. Высоты.

Для **__control87_2**возвращается значение 1, которое указывает на успешное выполнение.

## <a name="remarks"></a>Примечания

Функция **_control87** получает и задает управляющее слово с плавающей запятой. Управляющее слово с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в зависимости от платформы. **_Control87** также можно использовать для маскирования или раскрытия исключений с плавающей запятой. Если значение параметра *Mask* равно 0, **_control87** получает управляющее слово с плавающей запятой. Если параметр *Mask* имеет ненулевое значение, то для управляющего слова задается новый параметр: Для любого бита (то есть равного 1) в маске соответствующий битв *New* используется для обновления управляющего слова. Иными словами, **фпкнтрл** = ((**фпкнтрл** & ~*Mask*) &#124; (*Новая* & *Маска*)), где **фпкнтрл** — это управляющее слово с плавающей запятой.

> [!NOTE]
> По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .

**_controlfp** — это независимая от платформы переносимая версия **_control87** , которая почти идентична функции **_control87** . Если код предназначен для нескольких платформ, используйте **_controlfp** или **_controlfp_s**. Различие между **_control87** и **_controlfp** заключается в том, как они воспринимают ненормальные значения. Для платформ x86, x64, ARM и ARM64 **_control87** может устанавливать и очищать маску исключения денормализованного операнда. **_controlfp** не изменяет маску исключения денормализованного операнда. В следующем примере показано это различие.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Возможные значения для константы маски (*маски*) и новых значений элементов управления (*новые*) отображаются в таблице управляющие маски и значения элементов управления. Используйте перечисленные ниже переносимые константы ( **_MCW_EM**, **_EM_INVALID**и т. д.) в качестве аргументов для этих функций вместо явного предоставления шестнадцатеричных значений.

Платформы, производные от Intel x86, поддерживают НОРМАЛЬные входные и выходные значения в оборудовании. В случае x86 значения DENORMAL сохраняются. Платформы ARM и ARM64 и платформы x64 с поддержкой SSE2 позволяют использовать ненормальные операнды и результаты для очистки или принудительно применяют к нулю. Функции **_controlfp** и **_control87** предоставляют маску для изменения этого поведения. В следующем примере показано использование этой маски.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

На платформах ARM и ARM64 функции **_control87** и **_controlfp** применяются к регистру регистра fpscr. Только управляющее слово SSE2, хранящееся в регистре МКСКСР, затрагивает платформы x64. На платформах x86 **_control87** и **_controlfp** влияют на управляющие слова как для x87, так и для SSE2, если они есть.

Функция **__control87_2** позволяет управлять блоками с плавающей запятой X87 и SSE2 одновременно или отдельно. Чтобы повлиять на оба единицы, передайте адреса из двух целых чисел в **x86_cw** и **sse2_cw**. Если вы хотите только повлиять на одну единицу, передайте адрес для этого параметра, но передайте для другого значение 0 (**null**). Если для одного из этих параметров передано значение 0, данная функция не влияет на этот блок операций с плавающей запятой. Это полезно, когда в части кода используется модуль с плавающей запятой x87, а в другой — модуль с плавающей запятой SSE2.

Если вы используете **__control87_2** для задания различных значений для управляющих слов с плавающей запятой, то **_control87** или **_controlfp** могут не возвращать одно управляющее слово для представления состояния обоих единиц с плавающей запятой. В этом случае эти функции устанавливают флаг **EM_AMBIGUOUS** в возвращаемом целочисленном значении, чтобы указать несоответствие между двумя управляющими словами. Флаг **EM_AMBIGUOUS** является предупреждением о том, что возвращаемое управляющее слово может не представить состояние обоих управляющих слов с плавающей запятой точно.

На платформах ARM, ARM64 и x64 изменение режима бесконечности или точности с плавающей запятой не поддерживается. Если на платформе x64 используется маска управления точности, функция создает утверждение и вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

> [!NOTE]
> **__control87_2** не поддерживается на платформах ARM, ARM64 или x64. Если вы используете **__control87_2** и компилируете программу для платформ ARM, ARM64 или x64, компилятор выдает ошибку.

Эти функции игнорируются, если для компиляции используется [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md) . Среда CLR поддерживает только точность с плавающей запятой по умолчанию.

### <a name="control-word-masks-and-values"></a>Управление масками и значениями слов

Для маски **_MCW_EM** очистка маски задает исключение, которое позволяет устранить аппаратное исключение. Установка маски скрывает исключение. Если происходит **_EM_UNDERFLOW** или **_EM_OVERFLOW** , аппаратное исключение не создается до тех пор, пока не будет выполнена следующая инструкция с плавающей запятой. Чтобы создать исключение оборудования сразу после **_EM_UNDERFLOW** или **_EM_OVERFLOW**, вызовите инструкцию **фваит** MASM.

|Маска|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Ненормальное управление)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Маска исключения прерывания)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (Элемент управления бесконечности)<br /><br /> (Не поддерживается на платформах ARM или x64.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Элемент управления округлением)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Управление точностью)<br /><br /> (Не поддерживается на платформах ARM или x64.)|0x00030000|**_PC_24** (24 бита)<br /><br /> **_PC_53** (53 бит)<br /><br /> **_PC_64** (64 бит)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_cntrl87.c
// processor: x86
// compile by using: cl /W4 /arch:IA32 crt_cntrl87.c
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87 = 0;
    int result;

    // Show original x87 control word and do calculation.
    result = __control87_2(0, 0, &control_word_x87, 0 );
    printf( "Original: 0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    result = __control87_2(_PC_24, MCW_PC, &control_word_x87, 0 );
    printf( "24-bit:   0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    result = __control87_2( _CW_DEFAULT, MCW_PC, &control_word_x87, 0 );
    printf( "Default:  0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0009001f
0.1 * 0.1 = 1.000000000000000e-02
24-bit:   0x000a001f
0.1 * 0.1 = 9.999999776482582e-03
Default:  0x0009001f
0.1 * 0.1 = 1.000000000000000e-02
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)\
[_clear87, _clearfp](clear87-clearfp.md)\
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)\
[_controlfp_s](controlfp-s.md)
