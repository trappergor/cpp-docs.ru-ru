---
title: _InterlockedAddLargeStatistic | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 602cfb415c17c9e57d9fc1e932777cd1929e5f40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331401"
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Блок, относящийся только к системам Microsoft**  
  
 Выполняет блокируемое сложение, в которой первый операнд имеет 64-разрядное значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in, out] `Addend`  
 Указатель на первый операнд в операции добавления. Указывает значение заменяется результатом сложения.  
  
 [in] `Value`  
 Второй операнд; значение для первого операнда.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение второго операнда.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция не является атомарным, так как она реализована как два отдельных заблокированной инструкции. Atomic чтения 64-разрядной, возникшего в другом потоке во время выполнения это встроенная функция может привести значение несогласованные выполняется чтение.  
  
 Эта функция ведет себя как барьера чтения и записи. Дополнительные сведения см. в разделе [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)