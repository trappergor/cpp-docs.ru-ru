---
title: Встроенные функции _InterlockedExchange | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchange_rel
- _InterlockedExchange8_nf
- _InterlockedExchange_acq_cpp
- _InterlockedExchange_nf
- _InterlockedExchange64_nf
- _InterlockedExchange_HLEAcquire
- _InterlockedExchange_cpp
- _InterlockedExchange64_acq_cpp
- _InterlockedExchange64_acq
- _InterlockedExchange64_HLERelease
- _InterlockedExchange8_acq
- _InterlockedExchange16_acq
- _InterlockedExchange
- _InterlockedExchange64_HLEAcquire
- _InterlockedExchange8
- _InterlockedExchange64_rel
- _InterlockedExchange_acq
- _InterlockedExchange16
- _InterlockedExchange16_rel
- _InterlockedExchange16_nf
- _InterlockedExchange64
- _InterlockedExchange_HLERelease
- _InterlockedExchange64_cpp
- _InterlockedExchange8_rel
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchange8
- _InterlockedExchange64 intrinsic
- _InterlockedExchange_acq intrinsic
- InterlockedExchange64 intrinsic
- _InterlockedExchange64_acq intrinsic
- InterlockedExchange64_acq intrinsic
- _InterlockedExchange16_acq
- _InterlockedExchange8_acq
- _InterlockedExchange16
- _InterlockedExchange8_rel
- InterlockedExchange_acq intrinsic
- InterlockedExchange intrinsic
- _InterlockedExchange16_rel
- _InterlockedExchange16_nf
- _InterlockedExchange intrinsic
- _InterlockedExchange8_nf
ms.assetid: be2f232a-6301-462a-a92b-fcdeb8b0f209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7a450d683bfa2c358e26a4109a2e8a75c04e233
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716226"
---
# <a name="interlockedexchange-intrinsic-functions"></a>Встроенные функции _InterlockedExchange
**Блок, относящийся только к системам Microsoft**  
  
 Создает атомарные инструкция для присваивания заданного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
long _InterlockedExchange(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_acq(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLEAcquire(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLERelease(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_nf(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_rel(  
   long volatile * Target,  
   long Value  
);  
char _InterlockedExchange8(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_acq(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_nf(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_rel(  
   char volatile * Target,  
   char Value  
);  
short _InterlockedExchange16(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_acq(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_nf(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_rel(  
   short volatile * Target,  
   short Value  
);  
__int64 _InterlockedExchange64(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_acq(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLEAcquire(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLERelease(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_nf(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_rel(  
   __int64 volatile * Target,  
   __int64 Value  
);  
```  
  
#### <a name="parameters"></a>Параметры  
*Целевой объект*<br/>
[in, out] Указатель на значение для обмена. Функция присваивает этой переменной `Value` и возвращает предыдущее значение.  
  
*Значение*<br/>
[in] Значение для обмена со значением, на которые указывают `Target`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает начальное значение, на которое указывает `Target`.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|Верхний колонтитул|  
|---------------|------------------|------------|  
|`_InterlockedExchange`, `_InterlockedExchange8`, `_InterlockedExchange16`, `_InterlockedExchange64`|x86, ARM, x64|\<Intrin.h >|  
|`_InterlockedExchange_acq`, `_InterlockedExchange_nf`, `_InterlockedExchange_rel`, `_InterlockedExchange8_acq`, `_InterlockedExchange8_nf`, `_InterlockedExchange8_rel`, `_InterlockedExchange16_acq`, `_InterlockedExchange16_nf`, `_InterlockedExchange16_rel`, `_InterlockedExchange64_acq`, `_InterlockedExchange64_nf`, `_InterlockedExchange64_rel`,|ARM|\<Intrin.h >|  
|`_InterlockedExchange_HLEAcquire`, `_InterlockedExchange_HLERelease`, `_InterlockedExchange64_HLEAcquire`, `_InterlockedExchange64_HLERelease`|x86, x64|\<immintrin.h >|  
  
## <a name="remarks"></a>Примечания  
 `_InterlockedExchange` предоставляет встроенную поддержку компилятора для пакета SDK Windows Win32 [InterlockedExchange](/windows/desktop/api/winbase/nf-winbase-interlockedexchange) функции.  
  
 Существуют несколько вариантов `_InterlockedExchange`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.  
  
 Функция `_InterlockedExchange` работает с 32-разрядными целыми значениями, `_InterlockedExchange8`работает с 8-разрядными целыми значениями, `_InterlockedExchange16` работает с 16-разрядными целыми значениями и `_InterlockedExchange64` работает с 64-разрядными целыми значениями.  
  
 На платформах ARM используются встроенные функции с суффиксами `_acq` и `_rel` для получения и освобождения семантики, например, в начале и конце критической секции. Встроенные функции с суффиксом `_nf` («без границ») не действуют как барьер памяти.  
  
 На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision (HLE), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования. Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## <a name="example"></a>Пример  
 Пример использования `_InterlockedExchange`, см. в разделе [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)