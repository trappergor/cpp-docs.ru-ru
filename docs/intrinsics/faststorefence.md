---
title: "__faststorefence | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70999adc4bba03b3a8b00ad10330b18c68695af8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="faststorefence"></a>__faststorefence
**Блок, относящийся только к системам Microsoft**  
  
 Гарантирует, что каждая предыдущая ссылка на память, включая ссылки как на память чтения, так и на память записи, являются глобально видимыми до создания последующей ссылки на память.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __faststorefence();  
```  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__faststorefence`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Создает последовательность инструкций барьера полной памяти, которая гарантирует, что операции чтения и записи выдаются до того, как встроенные события становятся глобально видимыми перед тем, как продолжится выполнение. Эффект сравним со встроенной инструкцией `_mm_mfence` на всех платформах x64.  
  
 На платформе AMD64 этот процесс создает инструкцию, которая является барьером записи и позволяет работать быстрее, чем инструкция `sfence`. Для критичного по времени кода встроенную инструкцию вместо `_mm_sfence` следует использовать только на платформах AMD64. На платформах Intel x64 инструкция `_mm_sfence` будет выполняться быстрее.  
  
 Эта процедура доступна только как встроенная функция.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)