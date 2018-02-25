---
title: "__rdtsc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcf10bebb17096f29e2c96c9d66c631598d023aa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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