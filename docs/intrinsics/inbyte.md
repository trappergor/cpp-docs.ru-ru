---
title: __inbyte | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad2e02d4e1bc1ee5d1694769b2ec217cd7acbaba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329833"
---
# <a name="inbyte"></a>__inbyte
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки `in` инструкции, возвращая один байт чтения из портом, указанным `Port`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Port`  
 Порт, из которого выполняется чтение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Байт, считанный из указанного порта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__inbyte`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="remarks"></a>Примечания  
 Эта процедура доступна только как встроенная функция.  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)