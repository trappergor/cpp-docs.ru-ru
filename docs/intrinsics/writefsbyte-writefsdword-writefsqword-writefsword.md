---
title: "__writefsbyte __writefsdword, __writefsqword __writefsword | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __writefsword
- __writefsbyte
- __writefsqword
- __writefsdword
dev_langs: C++
helpviewer_keywords:
- writefsbyte intrinsic
- __writefsword intrinsic
- writefsqword intrinsic
- writefsdword intrinsic
- __writefsdword intrinsic
- __writefsqword intrinsic
- __writefsbyte intrinsic
- writefsword intrinsic
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf3324d45193ce19ae1e46d9f02268f43afc51b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="writefsbyte-writefsdword-writefsqword-writefsword"></a>__writefsbyte, __writefsdword, __writefsqword, __writefsword
**Блок, относящийся только к системам Microsoft**  
  
 Запись в папку, указанную в качестве смещения относительно начала FS сегмента памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __writefsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writefsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writefsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writefsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Offset`  
 Смещение от начала FS для записи.  
  
 [in] `Data`  
 Значение для записи.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__writefsbyte`|x86|  
|`__writefsword`|x86|  
|`__writefsdword`|x86|  
|`__writefsqword`|x86|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эти процедуры доступны только как встроенные объекты.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)