---
title: "_controlfp_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: 28
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 4345539f7ecd836280bed94c4bb2b125dfa08107
ms.contentlocale: ru-ru
ms.lasthandoff: 02/28/2017

---
# <a name="controlfps"></a>_controlfp_s
Возвращает и задает управляющее слово блока операций с плавающей запятой. Это версия функции [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `currentControl`  
 Значения битов в текущем управляющем слове.  
  
 `newControl`  
 Значения битов в новом управляющем слове.  
  
 `mask`  
 Маска для установки битов нового управляющего слова.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успешного выполнения или код ошибки `errno`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_controlfp_s` — это независимая от платформы и более безопасная версия функции `_control87`, которая получает управляющее слово с плавающей запятой в адрес, хранящийся в `currentControl`, и задает его с помощью `newControl`. Биты в значениях показывают состояние элемента управления блоком операций с плавающей запятой. Состояние элемента управления блока операций с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой в зависимости от платформы. Можно также использовать функцию `_controlfp_s` для маскирования и демаскирования исключений, связанных с операциями с плавающей запятой.  
  
 Если значение для `mask` равно 0, функция `_controlfp_s` получает управляющее слово блока операций с плавающей запятой и сохраняет извлеченное значение в `currentControl`.  
  
 Если значение `mask` отлично от нуля, задается новое значение управляющего слова: для любого включенного бита (то есть равного 1) в параметре `mask` соответствующий бит в параметре `new` используется для обновления управляющего слова. Другими словами, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)), где `fpcntrl` — управляющее слово блока операций с плавающей запятой. В этом сценарии `currentControl` получает значение после завершения изменения; это не старое битовое значение управляющего слова.  
  
> [!NOTE]
>  По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .  
  
 Функция `_controlfp_s` почти идентична функции `_control87` на платформах Intel (x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] и ARM. Если приложение предназначено для платформы x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] или ARM, можно использовать функцию `_control87` или `_controlfp_s`.  
  
 Разница между функциями `_control87` и `_controlfp_s` состоит в способе обработки значения `DENORMAL`. В случае платформ Intel (x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] и ARM функция `_control87` может устанавливать и очищать маску исключения DENORMAL OPERAND. Функция `_controlfp_s` не изменяет маску исключения DENORMAL OPERAND. В следующем примере показано это различие.  
  
```C  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 Возможные значения константы маски (`mask`) и новые управляющие значения (`newControl`) показаны в следующей таблице шестнадцатеричных значений. В аргументах этих функций вместо явных шестнадцатеричных значений следует использовать перечисленные ниже переносимые константы (`_MCW_EM`, `_EM_INVALID` и т. д.).  
  
 Платформы на основе Intel (x86) аппаратно поддерживают входные и выходные значения DENORMAL. В случае x86 значения DENORMAL сохраняются. Платформа ARM и платформы [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], в которых имеется поддержка SSE2, позволяют сбрасывать операнды и результаты DENORMAL (т. е., принудительно задавать для них нулевые значения). Функции `_controlfp_s`, `_controlfp` и `_control87` предоставляют маску для изменения такого поведения. В следующем примере показано использование этой маски:  
  
```C  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 На платформах ARM функция `_controlfp_s` применяется к регистру FPSCR. В архитектурах [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] затрагивается только управляющее слово SSE2, хранящееся в регистре MXCSR. На платформах Intel (x86) функция `_controlfp_s` влияет на управляющие слова как для x87, так и для SSE2 (при наличии). Два управляющих слова могут быть разными (например, в результате предыдущего вызова функции [__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)); в случае, если между управляющими словами имеется расхождение, `_controlfp_s` устанавливает флаг `EM_AMBIGUOUS` и `currentControl`. Это предупреждение о том, что возвращенное управляющее слово может неточно представлять состояние обоих управляющих слов блоков операций с плавающей запятой.  
  
 В архитектурах ARM и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] изменение режима бесконечности или точности чисел с плавающей запятой не поддерживается. Если маска управления точностью используется на платформе [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], функция создает утверждение и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Если маска задана неправильно, эта функция создает исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает `EINVAL` и задает для `errno` значение `EINVAL`.  
  
 Эта функция учитывается при использовании [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) компиляции, поскольку общеязыковой среды выполнения (CLR) поддерживает только точность чисел с плавающей запятой по умолчанию.  
  
### <a name="mask-constants-and-values"></a>Маска констант и значений  
  
 При очистке маски `_MCW_EM` задается исключение, которое допускает аппаратное исключение; установка маски скрывает это исключение. Если возникает исключение `_EM_UNDERFLOW` или `_EM_OVERFLOW`, аппаратное исключение не создается, пока не будет выполняться следующая операция с плавающей запятой. Чтобы аппаратное исключение возникало сразу после `_EM_UNDERFLOW` или `_EM_OVERFLOW`, следует вызвать инструкцию FWAIT MASM.  
  
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
|`_controlfp_s`|\<float.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
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
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
