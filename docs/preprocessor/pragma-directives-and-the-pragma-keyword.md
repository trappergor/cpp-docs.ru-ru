---
title: "Директивы pragma и ключевое слово __Pragma | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#pragma'
dev_langs: C++
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 845c2fab98d246ccee51aff721b1ceb011e3803c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>Директивы Pragma и ключевое слово __Pragma
Директивы pragma определяют возможности компилятора для конкретного компьютера или операционной системы. Ключевое слово `__pragma`, характерное для компилятора Microsoft, позволяет кодировать директивы pragma в определениях макросов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## <a name="remarks"></a>Примечания  
 Каждая реализация C и C++ поддерживает некоторые возможности, уникальные для хост-компьютера или операционной системы. Некоторые программы, например, должны осуществлять точный контроль над областями памяти, где размещаются данные, или контролировать способ получения параметров определенными функциями. Директивы `#pragma` предлагают каждому компилятору возможность предоставлять функции для конкретного компьютера и операционной системы, сохраняя общую совместимость с языками C и C++.  
  
 Директивы pragma характерны для конкретного компьютера или операционной системы по определению и обычно отличаются для каждого компилятора. Директивы pragma можно использовать в условных операторах для обеспечения новой функциональности препроцессора или для предоставления компилятору сведений, определенных реализацией.  
  
 `token-string` — это последовательность символов, которые предоставляют определенную инструкцию компилятора и аргументы, если таковые имеются. Знак числа (**#**) должен быть первым символом пустого пространства в строке, которая содержит директиву pragma; символы-разделители можно разделить знак числа и слово «pragma». После `#pragma` введите любой текст, который преобразователь может проанализировать как токены предварительной обработки. Аргумент `#pragma` подлежит расширению макроса.  
  
 Если компилятор обнаруживает нераспознаваемую директиву pragma, он выдает предупреждение и продолжает компиляцию.  
  
 Компиляторы Microsoft C и C++ распознают следующие директивы pragma.  
  
||||  
|-|-|-|  
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|  
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[component](../preprocessor/component.md)|[соответствует](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|  
|[data_seg](../preprocessor/data-seg.md)|[Рекомендуется использовать](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|  
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[цикл](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|  
|[управляемые](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|  
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[неуправляемые](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1. Поддерживается только компилятором C++.  
  
## <a name="pragmas-and-compiler-options"></a>Директивы pragma и параметры компилятора  
 Директивы pragma предоставляют те же функциональные возможности, что и параметры компилятора. При обнаружении директивы pragma в исходном коде она переопределяет поведение, заданное параметром компилятора. Например, если вы указали [/zp8](../build/reference/zp-struct-member-alignment.md), можно переопределить этот параметр компилятора для определенных разделов кода с помощью [пакет](../preprocessor/pack.md):  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## <a name="the-pragma-keyword"></a>Ключевое слово __pragma()  
 **Только к системам Майкрософт**  
  
 Компилятор также поддерживает ключевое слово `__pragma`, которое имеет те же функциональные возможности, что и директива `#pragma`, но может использоваться внутри определения макроса. `#pragma` Директива не может использоваться в определении макроса, поскольку компилятор интерпретирует символ номера (#) в директиве как [строковый оператор (#)](../preprocessor/stringizing-operator-hash.md).  
  
 В следующем примере кода показано, как использовать ключевое слово `__pragma` в макросе. Этот код — отрывок из заголовка mfcdual.h в образце ACDUAL, представленном в разделе "Примеры поддержки COM компилятором".  
  
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
  
 **Завершить к системам Microsoft**  
  
## <a name="see-also"></a>См. также  
 [Справочник по препроцессору C/C++](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Прагмы C](../c-language/c-pragmas.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)