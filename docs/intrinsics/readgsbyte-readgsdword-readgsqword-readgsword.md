---
title: __readgsbyte __readgsdword, __readgsqword __readgsword | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
dev_langs:
- C++
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00f71faa5a7b81931c8ee3fbce00ea4b7e66249b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541681"
---
# <a name="readgsbyte-readgsdword-readgsqword-readgsword"></a>__readgsbyte, __readgsdword, __readgsqword, __readgsword
**Блок, относящийся только к системам Microsoft**  
  
 Прочитать память из расположения, указанной в качестве смещения относительно начала сегмент GS.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Offset`  
 Смещение от начала `GS` считаны.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Содержимое памяти байт, слово, двойное слово или quadword (как указано в имени функции, вызываемой) в расположении `GS:[Offset]`.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__readgsbyte`|X64|  
|`__readgsdword`|X64|  
|`__readgsqword`|X64|  
|`__readgsword`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эти встроенные функции доступны только в режиме ядра и процедуры доступны только как встроенные функции.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)