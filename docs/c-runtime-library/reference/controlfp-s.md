---
title: "_controlfp_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_controlfp_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "controlfp_s"
  - "_controlfp_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_controlfp_s - функция"
  - "controlfp_s - функция"
  - "EM_AMBIGUOUS"
  - "функции с плавающей запятой, задание контрольного слова"
  - "числа с плавающей запятой, контрольное слово"
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _controlfp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает и задает управляющее слово с плавающей точкой.  В этой версии [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### Параметры  
 `currentControl`  
 Текущее битовое значение управляющего слова.  
  
 `newControl`  
 Значения бит в новом управляющем слове.  
  
 `mask`  
 Маска для установки битов нового управляющего слова.  
  
## Возвращаемое значение  
 Ноль в случае успешного выполнения или значение `errno` кода ошибки.  
  
## Заметки  
 Функция `_controlfp_s` \- это платформонезависимая и более безопасная версия функции `_control87`, которая получает управляющее слово с плавающей точкой по адресу, который хранится в `currentControl` и устанавливает его с помощью `newControl`.  Биты в значениях указывают состояние управления с плавающей точкой.  Управляющее состояние с плавающей точкой позволяет программе изменять точность, округление и режимы бесконечности математического пакета чисел с плавающей точкой в зависимости от платформы.  Можно также использовать `_controlfp_s` в маскирования и демаскирования исключений с плавающей точкой.  
  
 Если значение `mask` равно 0, то `_controlfp_s` получает управляющее слово с плавающей точкой и сохраняет полученное значение в `currentControl`.  
  
 Если `mask` отлично от нуля, задаётся новое значение управляющего слова: Для любого заданного бита \(то есть, равного 1\) в `mask`, соответствующий бит в `new` используется для обновления управляющего слова.  Другими словами, `fpcntrl` `=` \(\(`fpcntrl` `& ~mask`\) &#124; \(`new & mask`\)\), где `fpcntrl` \- управляющее слово с плавающей точкой.  В этом сценарии для `currentControl` задается значение после внесения изменений; это не старое битовое значение управляющего слова.  
  
> [!NOTE]
>  По умолчанию библиотеки времени выполнения маскируют все исключения с плавающей точкой.  
  
 `_controlfp_s` почти идентична функции `_control87` на Intel \(x86\), [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] и ARM платформах.  Если приложение разрабатывается для x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], или ARM платформ, можно использовать `_control87` или `_controlfp_s`.  
  
 Разница между `_control87` и `_controlfp_s` состоит в том, как они обрабатывают значения `DENORMAL`.  Для Intel \(x86\), [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] и ARM платформ `_control87` может устанавливать и убирать маску исключения DENORMAL OPERAND  `_controlfp_s` не изменяет маску исключения DENORMAL OPERAND  В следующем примере показано это различие.  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 Возможные значения константы маски \(`mask`\) и новые значения управления \(`newControl`\) показаны в следующей таблице шестнадцатеричных значений.  Вместо того, чтобы явно указывать шестнадцатеричные значения, следует использовать переносимые константы, перечисленные ниже \(`_MCW_EM`, `_EM_INVALID` и т д\) для аргументов к этим функциям.  
  
 Производные от Intel \(x86\) платформы поддерживают в оборудовании значения DENORMAL во входных и выходных данных.  x86 сохраняет значения DENORMAL.  Платформа ARM и платформы [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], обладающие поддержкой SSE2, включают сохранение операндов и результатов DENORMAL, или их приравнивание к нулю.  Функции `_controlfp_s`, `_controlfp` и `_control87` предоставляют маску для изменения такого поведения.  В следующем примере показано использование этой маски:  
  
```  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 На платформах ARM, функция `_controlfp_s` применяется к регистру FPSCR.  В архитектурах [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] затрагивается только управляющее слово SSE2, хранящееся в регистре MXCSR.  На платформах Intel \(x86\) `_controlfp_s` влияет на управляющие слова как для x87, так и для SSE2, если они есть.  Два управляющих слова могут быть несогласованы друг с другом \(из\-за предыдущего вызова [\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md), например\); если между двумя управляющими словами есть несогласованность, `_controlfp_s` устанавливает флаг `EM_AMBIGUOUS` в `currentControl`.  Это предупреждение о том, что возвращенное управляющее слово не может точно представлять состояние обоих управляющих слов с плавающей точкой.  
  
 В архитектурах ARM и [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] не поддерживается изменение режима бесконечности или точности чисел с плавающей точкой.  Если маска управления точностью используется на платформе [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], то функция создает утверждение и вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Если маска задана неправильно, эта функция создает исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `EINVAL` и устанавливает `errno` в значение `EINVAL`.  
  
 Эта функция игнорируется в случае использования [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) или **\/clr:pure** для компилирования, поскольку среда CLR поддерживает только точность чисел с плавающей точкой по умолчанию.  
  
 **Шестнадцатеричные значения**  
  
 Для маски `_MCW_EM`, её очистка задает исключение, которое допускает аппаратное исключение; установка маски скрывает исключение.  Если возникает `_EM_UNDERFLOW` или `_EM_OVERFLOW`, не аппаратное исключение не создается до тех пор, пока не выполнится следующая инструкций с плавающей точкой.  Для создания аппаратного исключения сразу после `_EM_UNDERFLOW` или `_EM_OVERFLOW`, следует вызвать инструкцию MASM FWAIT.  
  
|Маска|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|  
|-----------|--------------------------------|---------------|--------------------------------|  
|`_MCW_DN` \(управление Denormal\)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` \(маска исключения прерывания\)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` \(управление бесконечностью\)<br /><br /> \(Не поддерживается на платформах [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] или ARM\).|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` \(управление округлением\)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` \(управление точностью\)<br /><br /> \(Не поддерживается на платформах [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] или ARM\).|0x00030000|`_PC_24` \(24 бита\)<br /><br /> `_PC_53` \(53 бита\)<br /><br /> `_PC_64` \(64 бита\)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_controlfp_s`|\<float.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
//  
  
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
  
## Output  
  
```  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)