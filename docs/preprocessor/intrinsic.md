---
title: "Встроенная функция | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
dev_langs: C++
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d44a347f8f6cf6e502d3cc22435ed441a000f894
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="intrinsic"></a>intrinsic
Указывает, что функции, заданные в списка аргументов этой директивы, вызываются как встроенные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma intrinsic( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>Примечания  
 **Встроенная функция** pragma указывает компилятору, что поведение функции известно.  Компилятор может вызвать функцию и не заменять вызов функции подставляемыми инструкциями, если это позволит повысить производительность.  
  
 Ниже перечислены функции библиотеки со встроенными формами. Один раз **встроенная функция** директивы, он начинает действовать с первого определения функции, содержащее указанную встроенную функцию. Действие продолжается до конца исходного файла, либо во внешний вид **функция** pragma, указав ту же встроенную функцию. **Встроенная функция** pragma может использоваться только за пределами определения функции — на глобальном уровне.  
  
 Следующие функции имеют встроенные формы, и при указании используются встроенные формы [/Oi](../build/reference/oi-generate-intrinsic-functions.md):  
  
|||||  
|-|-|-|-|  
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|  
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|  
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|  
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||  
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||  
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||  
  
 Программы, в которых используются встроенные функции, выполняются быстрее, поскольку они не порождают дополнительную нагрузку, связанную с вызовом функций. Однако они могут иметь больший размер, поскольку в них создается дополнительный код.  
  
 **x86 конкретных**  
  
 Встроенные функции _disable и _enable создают инструкции режима ядра, включающие и отключающие прерывания. Они могут использоваться в драйверах, работающих в режиме ядра.  
  
## <a name="example"></a>Пример  
 Скомпилируйте следующий код из командной строки с параметрами "cl -c -FAs sample.c" и просмотрите файл sample.asm. Вы увидите, что в нем включены инструкции CLI и STI для процессоров x86.  
  
```  
// pragma_directive_intrinsic.cpp  
// processor: x86  
#include <dos.h>   // definitions for _disable, _enable  
#pragma intrinsic(_disable)  
#pragma intrinsic(_enable)  
void f1(void) {  
   _disable();  
   // do some work here that should not be interrupted  
   _enable();  
}  
int main() {  
}  
```  
  
 **Конец x86 определенного**  
  
 Функции с плавающей запятой, перечисленные ниже, не имеют полноценных встроенных форм. Однако у них есть версии, позволяющие передавать аргументы напрямую в микросхему операций с плавающей запятой, а не помещать их в стек программы:  
  
|||||  
|-|-|-|-|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)||  
  
 Функции с плавающей запятой, перечисленные ниже имеют полноценных встроенных форм, при указании [/Oi](../build/reference/oi-generate-intrinsic-functions.md), [/Og](../build/reference/og-global-optimizations.md), и [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) (или любой параметр, который содержится параметр/Og: [/ Ox](../build/reference/ox-full-optimization.md), [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)и/O2):  
  
|||||  
|-|-|-|-|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)||||  
  
 Можно использовать [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) или [/Za](../build/reference/za-ze-disable-language-extensions.md) для переопределения поколения true встроенных параметров с плавающей запятой. В этом случае функции будут создаваться как библиотечные процедуры, которые передают аргументы напрямую в микросхему операций с плавающей запятой, а не в стек программы.  
  
 В разделе [# pragma функция](../preprocessor/function-c-cpp.md) сведения и пример о том, как включить или отключить встроенные функции в блоке исходного текста.  
  
## <a name="see-also"></a>См. также  
 [Директивы pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)