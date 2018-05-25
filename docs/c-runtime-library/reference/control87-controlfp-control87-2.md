---
title: _control87, _controlfp, __control87_2 | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48d0c3107bf2edc09017ea138e4c8024ce328dd8
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2

Возвращает и задает управляющее слово блока операций с плавающей запятой. Более безопасная версия **_controlfp** , см. раздел [_controlfp_s](controlfp-s.md).

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

*new*<br/>
Значения битов в новом управляющем слове.

*Маска*<br/>
Маска для установки битов нового управляющего слова.

*x86_cw*<br/>
Заполняется управляющим словом для блока операций с плавающей запятой x87. Передайте 0 (**NULL**) для установки только управляющее слово SSE2.

*sse2_cw*<br/>
Управляющее слово для блока операций с плавающей запятой SSE. Передайте 0 (**NULL**) для установки только x87 управляющее слово.

## <a name="return-value"></a>Возвращаемое значение

Для **_control87** и **_controlfp**, возвращается биты в значении указывают состояние элемента управления с плавающей запятой. Полные определения битов, возвращаемых **_control87**, число с плавающей запятой в разделе. З.

Для **__control87_2**, возвращаемое значение-1, что означает успешное завершение.

## <a name="remarks"></a>Примечания

**_Control87** функция возвращает и задает управляющее слово. Управляющее слово блока операций с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой в зависимости от платформы. Можно также использовать **_control87** для маскирования и демаскирования связанных исключений с плавающей запятой. Если значение для *маска* равен 0, **_control87** получает управляющее слово. Если *маска* — не равно нулю, устанавливается новое значение управляющего слова: для какой-либо бит на (то есть, равного 1) в *маска*, соответствующий бит в *новый* используется для обновления элемента управления Microsoft Word. Другими словами **fpcntrl** = ((**fpcntrl** & ~*маска*) &#124; (*новый* & *маска*)) где **fpcntrl** является управляющее слово.

> [!NOTE]
> По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .

**_controlfp** — это независимая от платформы, переносимая версия **_control87**. Он очень похож на **_control87** функции в x86, x64 и на платформах ARM. Если вы используете x86, x64 или платформы ARM, используйте **_control87** или **_controlfp**.

Разница между **_control87** и **_controlfp** в способе обработки значения DENORMAL. X86, x64 и платформы ARM **_control87** может устанавливать и очищать маску исключения DENORMAL OPERAND. **_controlfp** не изменяет маску исключения DENORMAL OPERAND. В следующем примере показано это различие.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Возможные значения константы маски (*маска*) и новые управляющие значения (*новый*) показаны в следующей таблице шестнадцатеричных значений. Использовать перечисленные ниже переносимые константы (**_MCW_EM**, **_EM_INVALID**, и так далее) в аргументах этих функций вместо явных шестнадцатеричных значений.

Производный x86 платформы Intel поддерживают СБРАСЫВАТЬ входные и выходные значения. В случае x86 значения DENORMAL сохраняются. Платформа ARM и x64 поддерживаемых платформ SSE2, позволяют СБРАСЫВАТЬ операнды и результаты для удаленных или принудительно равным нулю. **_Controlfp** и **_control87** предоставляют маску для изменения этого поведения. В следующем примере показано использование этой маски.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

На платформах ARM **_control87** и **_controlfp** функции используются для регистра FPSCR. На x64 архитектур только управляющее слово SSE2, сохраняется регистр MXCSR снижается. На x86 платформы, **_control87** и **_controlfp** влияют на управляющие слова x87 и SSE2, если он имеется. Функция **__control87_2** позволяет x87 и единиц с плавающей запятой SSE2 контролировать вместе или по отдельности. Если требуется управлять обоими блоками, следует передать адреса двух целых чисел в **x86_cw** и **sse2_cw**. Если требуется только влияет на одну единицу, передать адрес для этого параметра, но передать 0 (**NULL**) для другого. Если для одного из этих параметров передано значение 0, данная функция не влияет на этот блок операций с плавающей запятой. Такая возможность может быть полезна в ситуациях, когда часть кода использует блок операций с плавающей запятой x87, и другая — блок операций с плавающей запятой SSE2. Если вы используете **__control87_2** в одной части программы и установить различные значения с плавающей запятой управляющих слов, а затем с помощью **_control87** или **_controlfp** для дальнейшего затем операций с управляющим словом, **_control87** и **_controlfp** может быть не в состоянии возвращать одно управляющее слово для представления состояние обеих блоков с плавающей запятой. В таком случае эти функции устанавливают **бита EM_AMBIGUOUS** флаг в возвращаемом целочисленном значении, означает, что может возникнуть несогласованность между двумя управляющими словами. Это предупреждение о том, что возвращенное управляющее слово может неточно представлять состояние обоих управляющих слов блоков операций с плавающей запятой.

На ARM и x64 архитектур, изменение режима бесконечности или точности с плавающей запятой не поддерживается. Если на x64 используется маска управления точности платформы, функция вызывает проверочное утверждение и вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md).

> [!NOTE]
> **__control87_2** не поддерживается на ARM или x64 архитектур. Если вы используете **__control87_2** и программа компилируется для ARM или x64 архитектур, компилятор выдает ошибку.

Эти функции игнорируются при использовании [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) компиляции, поскольку общеязыковой среды выполнения (CLR) поддерживает только точность чисел с плавающей запятой по умолчанию.

**Шестнадцатеричные значения**

Для **_MCW_EM** маска, очистка маски задает исключение, которое допускает аппаратное исключение; Установка маски скрывает исключение. Если **_EM_UNDERFLOW** или **_EM_OVERFLOW** происходит не аппаратное исключение не создается, пока не будет выполняться Далее операция с плавающей запятой. Чтобы аппаратное исключение сразу после **_EM_UNDERFLOW** или **_EM_OVERFLOW**, вызовите **FWAIT** инструкцию MASM.

|Маска|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Управление денормализацией)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (маска исключения прерывания)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (Управление бесконечностью)<br /><br /> (Не поддерживается на ARM или x64] платформы.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Управление округлением)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Управление точностью)<br /><br /> (Не поддерживается на ARM или x64 платформы.)|0x00030000|**_PC_24** (24 бита)<br /><br /> **_PC_53** (53 бита)<br /><br /> **_PC_64** (64-разрядная)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_cntrl87.c
// processor: x86
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87;

    // Show original x87 control word and do calculation.
    control_word_x87 = __control87_2(0, 0,
                                     &control_word_x87, 0);
    printf( "Original: 0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    control_word_x87 = __control87_2(_PC_24, MCW_PC,
                                     &control_word_x87, 0);
    printf( "24-bit:   0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,
                                     &control_word_x87, 0 );
    printf( "Default:  0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0001
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0x0001
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x0001
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
