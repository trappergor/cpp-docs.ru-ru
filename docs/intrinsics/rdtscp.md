---
title: __rdtscp | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtscp
dev_langs:
- C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d890afe9e19782f19442e8d95709b91a8680278
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329807"
---
# <a name="rdtscp"></a>__rdtscp
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки `rdtscp` инструкция записывает `TSC_AUX[31:0`] памяти и возвращает счетчик 64-разрядных временных меток (`TSC)` результат.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `Aux`  
 Указатель, который будет содержать содержимое регистра конкретного компьютера `TSC_AUX[31:0]`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число тактов 64-разрядное целое число без знака.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__rdtscp`|Семейство AMD NPT 0Fh или более поздней версии|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция приводит к возникновению ошибки `rdtscp` инструкции. Чтобы определить поддержку оборудования для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 27 `CPUInfo[3] (EDX)`. Этот бит — 1, если инструкция поддерживается и 0 в противном случае.  При выполнении кода, использующего встроенную на оборудовании, которое не поддерживает `rdtscp` инструкции, результаты будут непредсказуемыми.  
  
> [!CAUTION]
>  В отличие от `rdtsc`, `rdtscp` сериализации инструкция; тем не менее, компилятор можно переместить код вокруг это встроенная функция.  
  
 Интерпретация значения TSC в этом поколении оборудования отличается от более ранних версиях [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  В разделе руководства оборудования для получения дополнительной информации.  
  
 Смысл значения в `TSC_AUX[31:0]` зависит от операционной системы.  
  
## <a name="example"></a>Пример  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
```Output  
3363423610155519 ticks  
TSC_AUX was 0  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)