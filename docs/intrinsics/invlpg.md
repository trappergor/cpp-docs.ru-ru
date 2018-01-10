---
title: "__invlpg | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs: C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 919e1ff5d01dca587eff255f5a7164c41d2f04b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="invlpg"></a>__invlpg
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки x86 `invlpg` инструкции, которая делает недействительными буфера ассоциативной трансляции (TLB) для страницы, связанные с памятью, на который указывает `Address`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in]`Address`  
 64-разрядный адрес.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__invlpg`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Встроенная функция `__invlpg` выдает привилегированной инструкции и доступна только в режиме ядра с уровнем привилегий (Диалогового) 0.  
  
 Эта процедура доступна только как встроенная функция.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)