---
title: __readpmc | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readpmc
dev_langs:
- C++
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5072f49728a4ea9b7a323d3837997dd3d767358
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540105"
---
# <a name="readpmc"></a>__readpmc
**Блок, относящийся только к системам Microsoft**  
  
 Создает `rdpmc` инструкция, которая считывает производительность, наблюдение за счетчиком, определяемое `counter`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __readpmc(   
   unsigned long counter   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `counter`  
 Счетчик производительности, для чтения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение указанный счетчик производительности.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__readpmc`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)