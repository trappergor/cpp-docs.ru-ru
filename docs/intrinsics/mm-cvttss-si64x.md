---
title: _mm_cvttss_si64x | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvttss_si64x
dev_langs:
- C++
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4fd8aebb3f9a4f0078c8174aa25b9abb9378f1b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333633"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x
**Блок, относящийся только к системам Microsoft**  
  
 Создает x64 расширенной версии преобразования с числом с плавающей запятой одиночной точности усечение 64-разрядное целое число (`cvttss2si`) инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `value`  
 `__m128` Структуру, содержащую значения с плавающей запятой одиночной точности.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат преобразования первого значения с плавающей запятой в 64-разрядное целое число.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_cvttss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Встроенная функция отличается от `_mm_cvtss_si64x` только в том, что неточный преобразования усеченное в сторону нуля. Поскольку `__m128` структура представляет регистр XMM, создается инструкция перемещает данные из регистра XMM в системную память.  
  
 Эта процедура доступна только как встроенная функция.  
  
## <a name="example"></a>Пример  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__m128](../cpp/m128.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)