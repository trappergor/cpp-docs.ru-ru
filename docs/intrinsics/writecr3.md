---
title: __writecr3 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _writecr3
dev_langs:
- C++
helpviewer_keywords:
- _writecr3 intrinsic
ms.assetid: 959d49fa-69d5-47cf-88d2-7688367fe38f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 291cb73d3469264ad3b889cbd01c59622c4a370b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324708"
---
# <a name="writecr3"></a>__writecr3
**Блок, относящийся только к системам Microsoft**  
  
 Записывает значение `Data` CR3 регистрацию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void writecr3(   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Data`  
 Значение для записи в CR3 регистр.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__writecr3`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)