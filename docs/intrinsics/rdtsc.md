---
title: __rdtsc | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtsc
dev_langs:
- C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81b47a76b3045465d8c3c5c21a87020ee1e74a69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337084"
---
# <a name="rdtsc"></a>__rdtsc
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки `rdtsc` инструкции, которая возвращает отметку времени процессора. Отметка времени процессора регистрирует число тактов с момента последнего сброса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 64-разрядное целое число без знака, представляющее счетчик тактов.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта процедура доступна только как встроенная функция.  
  
 Интерпретация значения TSC в этом поколении оборудования отличается от более ранних версиях [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]. В разделе руководства оборудования для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
```Output  
3363423610155519 ticks  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)