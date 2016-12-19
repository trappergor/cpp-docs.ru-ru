---
title: "intrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "intrinsic_CPP"
  - "vc-pragma.intrinsic"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "intrinsic - прагма"
  - "прагмы, intrinsic"
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# intrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что функции, заданные в списка аргументов этой директивы, вызываются как встроенные.  
  
## Синтаксис  
  
```  
  
#pragma intrinsic( function1 [, function2, ...] )  
```  
  
## Заметки  
 Директива \#pragma **intrinsic** указывает компилятору, что поведение функции известно.  Компилятор может вызвать функцию и не заменять вызов функции подставляемыми инструкциями, если это позволит повысить производительность.  
  
 Ниже перечислены функции библиотеки со встроенными формами.  Объявленная директива \#pragma **intrinsic** начинает применяться для первого определения функции, в котором содержится заданная встроенная функция.  Ее действие продолжается до конца исходного файла или до появления директивы \#pragma **function**, задающей ту же самую встроенную функцию.  Директива \#pragma **function** может использоваться только за пределами определения функции — на глобальном уровне.  
  
 Следующие функции имеют встроенные формы, которые используются, если задан параметр [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md):  
  
|||||  
|-|-|-|-|  
|[\_disable](../intrinsics/disable.md)|[\_outp](../Topic/_outp,%20_outpw,%20_outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)|  
|[\_enable](../intrinsics/enable.md)|[\_outpw](../Topic/_outp,%20_outpw,%20_outpd.md)|[labs](../misc/labs-llabs.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|[\_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md)|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|[\_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||  
|[\_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[\_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset.](../c-runtime-library/reference/memset-wmemset.md)||  
|[\_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||  
  
 Программы, в которых используются встроенные функции, выполняются быстрее, поскольку они не порождают дополнительную нагрузку, связанную с вызовом функций. Однако они могут иметь больший размер, поскольку в них создается дополнительный код.  
  
 **Специфика для платформы x86**  
  
 Встроенные функции \_disable и \_enable создают инструкции режима ядра, включающие и отключающие прерывания. Они могут использоваться в драйверах, работающих в режиме ядра.  
  
## Пример  
 Скомпилируйте следующий код из командной строки с параметрами "cl \-c \-FAs sample.c" и просмотрите файл sample.asm. Вы увидите, что в нем включены инструкции CLI и STI для процессоров x86.  
  
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
  
 **Специфика для платформы x86 — окончание**  
  
 Функции с плавающей запятой, перечисленные ниже, не имеют полноценных встроенных форм.  Однако у них есть версии, позволяющие передавать аргументы напрямую в микросхему операций с плавающей запятой, а не помещать их в стек программы:  
  
|||||  
|-|-|-|-|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[pow](../Topic/pow,%20powf,%20powl.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../Topic/fmod,%20fmodf.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)||  
  
 Если задан параметр [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md), [\/Og](../build/reference/og-global-optimizations.md) и [\/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) \(или любой параметр, в котором содержится параметр \/Og: [\/Ox](../build/reference/ox-full-optimization.md), [\/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md) и \/O2\), то у следующих функций имеются полноценные встроенные формы:  
  
|||||  
|-|-|-|-|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../Topic/log,%20logf,%20log10,%20log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../Topic/log,%20logf,%20log10,%20log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)||||  
  
 Чтобы отключить создание полноценных вариантов функций с плавающей запятой, установите параметр компилятора [\/fp:strict](../build/reference/fp-specify-floating-point-behavior.md) или [\/Za](../build/reference/za-ze-disable-language-extensions.md).  В этом случае функции будут создаваться как библиотечные процедуры, которые передают аргументы напрямую в микросхему операций с плавающей запятой, а не в стек программы.  
  
 Дополнительные сведения о том, как включать или отключать встроенные функции в блоке исходного текста, а также примеры их использования см. в разделе [\#pragma function](../preprocessor/function-c-cpp.md).  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)