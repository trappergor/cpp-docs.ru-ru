---
title: "__addfsbyte __addfsword, __addfsdword | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
dev_langs: C++
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04478094ec318073567e603f1e96664b08a36d6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="addfsbyte-addfsword-addfsdword"></a>__addfsbyte, __addfsword, __addfsdword
**Блок, относящийся только к системам Майкрософт**  
  
 Добавить значение в ячейку памяти, указанной в качестве смещения относительно начала `FS` сегмента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __addfsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addfsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addfsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Offset`  
 Смещение от начала `FS`.  
  
 [in] `Data`  
 Значения для добавления в область памяти.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__addfsbyte`|x86|  
|`__addfsword`|x86|  
|`__addfsdword`|x86|  
  
## <a name="remarks"></a>Примечания  
 Эти процедуры доступны только как встроенные объекты.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__incfsbyte, \__incfsword, \__incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)   
 [__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)