---
title: __readcr3 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readcr3
dev_langs:
- C++
helpviewer_keywords:
- __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a632199dcc3318109a6b95f82d718ac3f26fa23
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="readcr3"></a>__readcr3
**Блок, относящийся только к системам Microsoft**  
  
 Считывает регистр CR3 и возвращает его значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __readcr3(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение в регистре CR3.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__readcr3`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)