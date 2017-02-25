---
title: "Директивы Pragma и ключевое слово __Pragma | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#pragma"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "#pragma - директивы, C/C++"
  - "__pragma - ключевое слово"
  - "pragma - директивы (#pragma)"
  - "pragma - директивы, C/C++"
  - "прагмы"
  - "прагмы, C/C++"
  - "препроцессор"
  - "препроцессор, прагмы"
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Директивы Pragma и ключевое слово __Pragma
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Директивы pragma определяют функции компилятора для конкретного компьютера или операционной системы.  Ключевое слово `__pragma`, характерное для компилятора Microsoft, позволяет кодировать директивы pragma в определениях макросов.  
  
## Синтаксис  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## Заметки  
 Каждая реализация C и C\+\+ поддерживает некоторые функции, уникальные для хост\-компьютера или операционной системы.  Некоторые программы, например, должны осуществлять точный контроль над областями памяти, где размещаются данные, или контролировать способ получения параметров определенными функциями.  Директивы `#pragma` предлагают каждому компилятору возможность предоставлять функции для конкретного компьютера и операционной системы, сохраняя общую совместимость с языками C и C\+\+.  
  
 Директивы pragma характерны для конкретного компьютера или операционной системы по определению и обычно отличаются для каждого компилятора.  Директивы pragma можно использовать в условных операторах для обеспечения новой функциональности препроцессора или для предоставления компилятору сведений, определенных реализацией.  
  
 `token-string` — это последовательность символов, которые предоставляют определенную инструкцию компилятора и аргументы, если таковые имеются.  Символ решетки \(**\#**\) должен быть первым отличным от пробела символом в строке, которая содержит директиву pragma; символы пробела могут разделять знак числа и слово pragma.  После `#pragma` введите любой текст, который преобразователь может проанализировать как токены предварительной обработки.  Аргумент `#pragma` подлежит расширению макроса.  
  
 Если компилятор обнаруживает нераспознаваемую директиву pragma, он выдает предупреждение и продолжает компиляцию.  
  
 Компиляторы Microsoft C и C\+\+ распознают следующие директивы pragma.  
  
||||  
|-|-|-|  
|[alloc\_text](../preprocessor/alloc-text.md)|[auto\_inline](../preprocessor/auto-inline.md)|[bss\_seg](../preprocessor/bss-seg.md)|  
|[check\_stack](../preprocessor/check-stack.md)|[code\_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[component](../Topic/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const\_seg](../preprocessor/const-seg.md)|  
|[data\_seg](../preprocessor/data-seg.md)|[deprecated](../Topic/deprecated%20\(C-C++\).md)|[detect\_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv\_access](../preprocessor/fenv-access.md)|[float\_control](../Topic/float_control.md)|[fp\_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include\_alias](../preprocessor/include-alias.md)|  
|[init\_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline\_depth](../preprocessor/inline-depth.md)|[inline\_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make\_public](../preprocessor/make-public.md)|  
|[managed](../preprocessor/managed-unmanaged.md)|[сообщение](../Topic/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers\_to\_members](../Topic/pointers_to_members.md) <sup>1</sup>|  
|[pop\_macro](../Topic/pop_macro.md)|[push\_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime\_checks](../Topic/runtime_checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict\_gs\_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../Topic/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1.  Поддерживается только компилятором C\+\+.  
  
## Директивы pragma и параметры компилятора  
 Директивы pragma предоставляют те же функциональные возможности, что и параметры компилятора.  При обнаружении директивы pragma в исходном коде она переопределяет поведение, заданное параметром компилятора.  Например, если задан параметр [\/Zp8](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md), можно переопределить этот параметр компилятора для определенных разделов кода с помощью [pack](../preprocessor/pack.md).  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## Ключевое слово \_\_pragma\(\)  
 **Блок, относящийся только к системам Microsoft**  
  
 Компилятор также поддерживает ключевое слово `__pragma`, которое имеет те же функциональные возможности, что и директива `#pragma`, но может использоваться внутри определения макроса.  Директиву `#pragma` невозможно использовать в определении макроса, поскольку компилятор интерпретирует символ номера \("\#"\) в директиве как [строковый оператор \(\#\)](../preprocessor/stringizing-operator-hash.md).  
  
 В следующем примере кода показано, как использовать ключевое слово `__pragma` в макросе.  Этот код — отрывок из заголовка mfcdual.h в образце ACDUAL, представленном в разделе "Примеры поддержки COM компилятором".  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Справочник по препроцессору C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Прагмы C](../c-language/c-pragmas.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)