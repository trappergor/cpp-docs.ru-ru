---
title: "_control87, _controlfp, __control87_2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "34"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee8d874a84d8f1246c0990b4bf29d07c28237057
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2
Возвращает и задает управляющее слово блока операций с плавающей запятой. Доступна более безопасная версия функции `_controlfp`; см. раздел [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `new`  
 Значения битов в новом управляющем слове.  
  
 `mask`  
 Маска для установки битов нового управляющего слова.  
  
 `x86_cw`  
 Заполняется управляющим словом для блока операций с плавающей запятой x87. Передайте 0 (`NULL`), чтобы задать только управляющее слово SSE2.  
  
 `sse2_cw`  
 Управляющее слово для блока операций с плавающей запятой SSE. Передайте 0 (`NULL`), чтобы задать только управляющее слово x87.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Для `_control87` и `_controlfp` биты возвращаемого значения показывают состояние управления блоком операций с плавающей запятой. Полные определения битов, возвращаемых функцией `_control87`, см. в файле FLOAT.H.  
  
 Для `__control87_2` возвращаемое значение равно 1, что означает успешное завершение.  
  
## <a name="remarks"></a>Примечания  
 Функция `_control87` получает и задает управляющее слово блока операций с плавающей запятой. Управляющее слово блока операций с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой в зависимости от платформы. Можно также использовать функцию `_control87` для маскирования и демаскирования исключений, связанных с операциями с плавающей запятой. Если значение для `mask` равно 0, функция `_control87` получает управляющее слово блока операций с плавающей запятой. Если значение `mask` отлично от нуля, задается новое значение управляющего слова: для любого включенного бита (то есть, равного 1) в параметре `mask` соответствующий бит в параметре `new` используется для обновления управляющего слова. Другими словами, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)), где `fpcntrl` — управляющее слово блока операций с плавающей запятой.  
  
> [!NOTE]
>  По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .  
  
 `_controlfp` — независимая от платформы, переносимая версия функции `_control87`. Она почти идентична функции `_control87` на платформах Intel (x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] и ARM. Если приложение предназначено для платформы x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] или ARM, используйте функцию `_control87` или `_controlfp`.  
  
 Разница между функциями `_control87` и `_controlfp` состоит в способе обработки значения DENORMAL. В случае платформ Intel (x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] и ARM функция `_control87` может устанавливать и очищать маску исключения DENORMAL OPERAND. Функция `_controlfp` не изменяет маску исключения DENORMAL OPERAND. В следующем примере показано это различие.  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 Возможные значения константы маски (`mask`) и новые управляющие значения (`new`) показаны в следующей таблице шестнадцатеричных значений. В аргументах этих функций вместо явных шестнадцатеричных значений следует использовать перечисленные ниже переносимые константы (`_MCW_EM`, `_EM_INVALID` и т. д.).  
  
 Платформы на основе Intel (x86) аппаратно поддерживают входные и выходные значения DENORMAL. В случае x86 значения DENORMAL сохраняются. Платформа ARM и платформы [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], в которых имеется поддержка SSE2, позволяют сбрасывать операнды и результаты DENORMAL (т. е., принудительно задавать для них нулевые значения). Функции `_controlfp` и `_control87` предоставляют маску для изменения такого поведения. В следующем примере показано использование этой маски.  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 На платформах ARM функции `_control87` и `_controlfp` применяются к регистру FPSCR. В архитектурах [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] затрагивается только управляющее слово SSE2, хранящееся в регистре MXCSR. На платформах Intel (x86) функции `_control87` и `_controlfp` влияют на управляющие слова как для x87, так и для SSE2 (при наличии). Функция `__control87_2` позволяет управлять блоками операций с плавающей запятой x87 и SSE2 как совместно, так и раздельно. Если требуется управлять обоими блоками, следует передать адреса двух целых чисел в параметры `x86_cw` и `sse2_cw`. Если требуется управлять только одним блоком, следует передать адрес для этого параметра, но передать 0 (NULL) для другого. Если для одного из этих параметров передано значение 0, данная функция не влияет на этот блок операций с плавающей запятой. Такая возможность может быть полезна в ситуациях, когда часть кода использует блок операций с плавающей запятой x87, и другая — блок операций с плавающей запятой SSE2. Если использовать функцию `__control87_2` в одной части программы и установить различные значения для управляющих слов блоков операций с плавающей запятой, а для дальнейших операций с управляющим словом использовать функцию `_control87` или `_controlfp`, функции `_control87` и `_controlfp` могут оказаться не в состоянии возвращать одно управляющее слово для представления состояние обеих блоков операций с плавающей запятой. В таком случае эти функции устанавливают в возвращаемом целочисленном значении флажок `EM_AMBIGUOUS`, указывающий на наличие несоответствия между двумя управляющими словами. Это предупреждение о том, что возвращенное управляющее слово может неточно представлять состояние обоих управляющих слов блоков операций с плавающей запятой.  
  
 В архитектурах ARM и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] изменение режима бесконечности или точности чисел с плавающей запятой не поддерживается. Если маска управления точностью используется на платформе [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], функция создает утверждение и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
> [!NOTE]
>  Функция `__control87_2` не поддерживается в архитектурах ARM и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]. Если используется функция `__control87_2` и программа компилируется для архитектуры ARM или [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], компилятор выдает ошибку.  
  
 Эти функции игнорируются при использовании [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) компиляции, поскольку общеязыковой среды выполнения (CLR) поддерживает только точность чисел с плавающей запятой по умолчанию.  
  
 **Шестнадцатеричные значения**  
  
 В случае маски `_MCW_EM` очистка маски задает исключение, которое допускает аппаратное исключение; установка маски скрывает исключение. Если возникает исключение `_EM_UNDERFLOW` или `_EM_OVERFLOW`, аппаратное исключение не создается, пока не будет выполняться следующая операция с плавающей запятой. Чтобы аппаратное исключение возникало сразу после `_EM_UNDERFLOW` или `_EM_OVERFLOW`, следует вызвать инструкцию MASM `FWAIT`.  
  
|Маска|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN` (управление денормализацией)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` (маска исключения прерывания)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` (управление бесконечностью)<br /><br /> (Не поддерживается на платформах ARM и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` (управление округлением)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` (управление точностью)<br /><br /> (Не поддерживается на платформах ARM и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].)|0x00030000|`_PC_24` (24 бита)<br /><br /> `_PC_53` (53 бита)<br /><br /> `_PC_64` (64 бита)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_control87`, `_controlfp`, `_control87_2`|\<float.h>|  
  
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
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)