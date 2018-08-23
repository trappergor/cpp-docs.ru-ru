---
title: __readmsr | Документация Майкрософт
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
ms.openlocfilehash: b3be04079de11642b2641260fdfe997d3fcb48d6
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539117"
---
# <a name="readmsr"></a>__readmsr
**Блок, относящийся только к системам Microsoft**  
  
 Создает `rdmsr` инструкция, которая считывает регистр конкретной модели, определяемое `register` и возвращает его значение.  
  
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
|`__readmsr`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта функция доступна только в режиме ядра и процедура доступна только как встроенная.  
  
 Дополнительные сведения см. в документации AMD.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)