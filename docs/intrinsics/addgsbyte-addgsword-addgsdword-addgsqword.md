---
title: __addgsbyte __addgsword, __addgsdword __addgsqword | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __addgsdword
- __addgsqword
- __addgsword_cpp
- __addgsword
- __addgsbyte_cpp
- __addgsqword_cpp
- __addgsbyte
- __addgsdword_cpp
dev_langs:
- C++
helpviewer_keywords:
- __addgsword intrinsic
- __addgsqword intrinsic
- __addgsdword intrinsic
- __addgsbyte intrinsic
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd5341dc4d47740410df01feadbd9e6aa3926a23
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721394"
---
# <a name="addgsbyte-addgsword-addgsdword-addgsqword"></a>__addgsbyte, __addgsword, __addgsdword, __addgsqword
**Блок, относящийся только к системам Microsoft**  
  
 Добавить значение в ячейку памяти, указанной в качестве смещения относительно начала `GS` сегмента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __addgsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addgsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addgsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __addgsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>Параметры  
*Смещение*<br/>
[in] Смещение от начала `GS`.  
  
*Данные*<br/>
[in] Значение, добавляемое в область памяти.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__addgsbyte`|X64|  
|`__addgsword`|X64|  
|`__addgsdword`|X64|  
|`__addgsqword`|X64|  
  
## <a name="remarks"></a>Примечания  
 Эти встроенные функции доступны только в режиме ядра, и эти процедуры доступны только как встроенные функции.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__incgsbyte, \__incgsword, \__incgsdword, \__incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)   
 [__readgsbyte, \__readgsdword, \__readgsqword, \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)