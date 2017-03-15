---
title: "ccosh, ccoshf, ccoshl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ccosh
- ccoshf
- ccoshl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ccosh
- ccoshf
- ccoshl
- complex/ccosh
- complex/ccoshf
- complex/ccoshl
dev_langs:
- C++
helpviewer_keywords:
- ccosh function
- ccoshf function
- ccoshl function
ms.assetid: 79667449-4edf-4948-bf6b-720adf2b3f3b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4626b5afbc81a5c747d62813aa5fab40c2b6a27b
ms.lasthandoff: 02/24/2017

---
# <a name="ccosh-ccoshf-ccoshl"></a>ccosh, ccoshf, ccoshl
Извлекает гиперболический косинус комплексного числа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_Dcomplex ccosh(   
   _Dcomplex z   
);  
_Fcomplex ccosh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex ccosh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex ccoshf(   
   _Fcomplex z   
);  
_Lcomplex ccoshl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `z`  
 Комплексное число, указывающее угол в радианах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Гиперболический косинус аргумента `z` в радианах.  
  
## <a name="remarks"></a>Примечания  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `ccosh`, которые принимают и возвращают значения `_Fcomplex` и `_Lcomplex`. В программе на языке C `ccosh` всегда принимает и возвращает значение `_Dcomplex` .  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Заголовок C|Заголовок C++|  
|-------------|--------------|------------------|  
|`ccosh`,               `ccoshf`, `ccoshl`|\<complex.h>|\<ccomplex>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)
