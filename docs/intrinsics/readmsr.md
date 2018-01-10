---
title: "__readmsr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __readmsr
dev_langs: C++
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec257195fafc6a63f6ac3cdc0b143643ae3ea9fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="readmsr"></a>__readmsr
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки `rdmsr` инструкции, которая считывает регистр конкретной модели, заданный в параметре `register` и возвращает его значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `register`  
 Модельнозависимого регистра для чтения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение в указанном регистре.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__readmsr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта функция доступна только в режиме ядра и процедура доступна только как встроенная функция.  
  
 Дополнительные сведения см. в документации AMD.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)