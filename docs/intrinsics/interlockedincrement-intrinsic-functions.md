---
title: "Встроенные функции _InterlockedIncrement | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedIncrement_acq
- _InterlockedIncrement16_rel_cpp
- _InterlockedIncrement16_cpp
- _InterlockedIncrement64_rel
- _InterlockedIncrement_rel
- _InterlockedIncrement64_nf
- _InterlockedIncrement16_acq_cpp
- _InterlockedIncrement_rel_cpp
- _InterlockedIncrement64
- _InterlockedIncrement64_rel_cpp
- _InterlockedIncrement16_nf
- _InterlockedIncrement16_rel
- _InterlockedIncrement16_acq
- _InterlockedIncrement_nf
- _InterlockedIncrement_acq_cpp
- _InterlockedIncrement64_cpp
- _InterlockedIncrement64_acq_cpp
- _InterlockedIncrement
- _InterlockedIncrement_cpp
- _InterlockedIncrement64_acq
- _InterlockedIncrement16
dev_langs: C++
helpviewer_keywords:
- _InterlockedIncrement64_rel intrinsic
- _InterlockedIncrement16_rel intrinsic
- InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16 intrinsic
- _InterlockedIncrement16_acq intrinsic
- _InterlockedIncrement_nf intrinsic
- _InterlockedIncrement_rel intrinsic
- _InterlockedIncrement64_nf intrinsic
- InterlockedIncrement_rel intrinsic
- InterlockedIncrement_acq intrinsic
- _InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16_nf intrinsic
- _InterlockedIncrement intrinsic
- _InterlockedIncrement64 intrinsic
- InterlockedIncrement64_rel intrinsic
- InterlockedIncrement64 intrinsic
- InterlockedIncrement16 intrinsic
- _InterlockedIncrement_acq intrinsic
- InterlockedIncrement intrinsic
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6185aee179febe77fa9f5b47793e4becd253e504
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="interlockedincrement-intrinsic-functions"></a>Встроенные функции _InterlockedIncrement
**Блок, относящийся только к системам Майкрософт**  
  
 Предоставляют встроенную поддержку компилятора для функции Win32 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] [InterlockedIncrement](http://msdn.microsoft.com/library/ms683614.aspx) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
long _InterlockedIncrement(  
   long * lpAddend  
);  
long _InterlockedIncrement_acq(  
   long * lpAddend  
);  
long _InterlockedIncrement_rel(  
   long * lpAddend  
);  
long _InterlockedIncrement_nf(  
   long * lpAddend  
);  
short _InterlockedIncrement16(  
   short * lpAddend  
);  
short _InterlockedIncrement16_acq(  
   short * lpAddend  
);  
short _InterlockedIncrement16_rel(  
   short * lpAddend  
);  
short _InterlockedIncrement16_nf (  
   short * lpAddend  
);  
__int64 _InterlockedIncrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedIncrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in, out] `lpAddend`  
 Указатель на переменную для увеличения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение, полученное после увеличения.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|Верхний колонтитул|  
|---------------|------------------|------------|  
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<Intrin.h >|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<Intrin.h >|  
  
## <a name="remarks"></a>Примечания  
 Существуют несколько вариантов `_InterlockedIncrement`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.  
  
 Функция `_InterlockedIncrement` работает с 32-разрядными целыми значениями, `_InterlockedIncrement16``_InterlockedIncrement64` работает с 16-разрядными целыми значениями и работает с 64-разрядными целыми значениями.  
  
 На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенная функция с суффиксом `_nf` («без границ») не действует как ограничитель памяти.  
  
 Переменная, на который указывает параметр `lpAddend`, должна быть выровнена по границе 32 разрядов; в противном случае эта функция не выполняется на многопроцессорных системах x86 и любой системе не-x86. Дополнительные сведения см. в разделе [выравнивание](../cpp/align-cpp.md).  
  
 Функция Win32 объявляется в `Wdm.h` или `Ntddk.h`.  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## <a name="example"></a>Пример  
 Пример использования `_InterlockedIncrement`, в разделе [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)