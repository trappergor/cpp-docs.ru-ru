---
title: _mm_cvtsi64x_ss | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtsi64x_ss
dev_langs:
- C++
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bb529e8aab204df85de2da0a2fdf4c820964239
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340610"
---
# <a name="mmcvtsi64xss"></a>_mm_cvtsi64x_ss
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] расширенная версия преобразование 64-разрядное целое число, которое скалярное значение с плавающей запятой одинарной точности (`cvtsi2ss`) инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `a`  
 `__m128` Структуру, содержащую четыре значения с плавающей запятой одиночной точности.  
  
 [in] `b`  
 64-разрядное целое, должны преобразовываться в значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `__m128` Структуры первый с плавающей запятой, значение которого является результатом преобразования. Три значения копируются изменились по сравнению с `a`.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_cvtsi64x_ss`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 `__m128` Структура представляет регистр XMM, поэтому эта встроенная функция позволяет значение `b` из системной памяти, который необходимо переместить в XMM зарегистрировать.  
  
 Эта процедура доступна только как встроенная функция.  
  
## <a name="example"></a>Пример  
  
```  
// _mm_cvtsi64x_ss.cpp  
// processor: x64  
  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtsi64x_ss)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    a.m128_f32[0] = 0;  
    a.m128_f32[1] = 0;  
    a.m128_f32[2] = 0;  
    a.m128_f32[3] = 0;  
    a = _mm_cvtsi64x_ss(a, b);  
  
    printf_s( "%lf %lf %lf %lf\n",  
              a.m128_f32[0], a.m128_f32[1],   
              a.m128_f32[2], a.m128_f32[3] );  
}  
```  
  
```Output  
54.000000 0.000000 0.000000 0.000000  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__m128](../cpp/m128.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)