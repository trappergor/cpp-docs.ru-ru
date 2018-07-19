---
title: __readmsr | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readmsr
dev_langs:
- C++
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e8196b25b1507c92542faa6dd8ca59b4632d8f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335917"
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