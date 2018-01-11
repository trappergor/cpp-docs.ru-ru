---
title: "_mm_stream_sd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_stream_sd
dev_langs: C++
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da88116f58c6e33d35a69ebb6ac2433a8fe8f4ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mmstreamsd"></a>_mm_stream_sd
**Блок, относящийся только к системам Microsoft**  
  
 Записывает данные в 64-разрядных расположение в памяти без избавляют кэшей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `Dest`  
 Указатель на расположение, куда будет записан в источнике данных.  
  
 [in] `Source`  
 128-разрядное значение, содержащее `double` значение для записи в его нижней 64 бита...  
  
## <a name="return-value"></a>Возвращаемое значение  
 Отсутствует.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция приводит к возникновению ошибки `movntsd` инструкции. Чтобы определить поддержку оборудования для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит равен 1, если оборудование поддерживает эту инструкцию и 0 в противном случае.  
  
 При выполнении кода, использующего `_mm_stream_sd` на оборудовании, которое не поддерживает встроенные `movntsd` инструкции, результаты будут непредсказуемыми.  
  
## <a name="example"></a>Пример  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
```Output  
d[0] = -1, d[1] = 1  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [_mm_stream_ss](../intrinsics/mm-stream-ss.md)   
 [_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)