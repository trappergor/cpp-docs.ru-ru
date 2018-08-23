---
title: "\"__rdtscp\" | Документация Майкрософт"
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
ms.openlocfilehash: a98f1e84f3ef09d3cef5d45028374b93887fc6d4
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540525"
---
# <a name="rdtscp"></a>__rdtscp
**Блок, относящийся только к системам Microsoft**  
  
 Создает `rdtscp` записывает инструкции, `TSC_AUX[31:0`] в памяти и возвращает счетчик отметок времени 64-разрядных (`TSC)` результат.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `Aux`  
 Указатель на расположение, которое будет содержать содержимое регистра конкретного компьютера `TSC_AUX[31:0]`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик тактов 64-разрядного целого числа без знака.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__rdtscp`|Семейство NPT AMD 0Fh или более поздней версии|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция создает `rdtscp` инструкции. Чтобы определить аппаратная поддержка для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 27 `CPUInfo[3] (EDX)`. Этот бит равен 1, если инструкция поддерживается и 0 в противном случае.  Если вы запустите код, использующий этой встроенной функции на оборудовании, которое не поддерживает `rdtscp` инструкции, результаты будут непредсказуемыми.  
  
> [!CAUTION]
>  В отличие от `rdtsc`, `rdtscp` сериализации инструкция; тем не менее, компилятор может переместить код этой проблемы внутренние.  
  
 Интерпретация TSC значения в этом поколении оборудования отличается от более ранних версий x64.  См. в разделе руководства оборудования, Дополнительные сведения.  
  
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
 Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)