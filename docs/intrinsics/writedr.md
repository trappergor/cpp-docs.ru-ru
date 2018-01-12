---
title: "__writedr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __writedr
dev_langs: C++
helpviewer_keywords: __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e58523995bfe3bb47d915e161a937149bcf4f78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="writedr"></a>__writedr
Записывает указанное значение регистра указанного отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __writedr(unsigned DebugRegister, unsigned DebugValue);  
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `DebugRegister`  
 Число от 0 до 7, определяющее отладочные регистр.  
  
 [in] `DebugValue`  
 Значение, записываемое отладочные регистр.  
  
## <a name="remarks"></a>Примечания  
 Эти встроенные функции доступны только в режиме ядра и процедуры доступны только как встроенные объекты.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__writedr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__readdr](../intrinsics/readdr.md)