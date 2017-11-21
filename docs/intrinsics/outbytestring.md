---
title: "__outbytestring | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __outbytestring
dev_langs: C++
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43ee5deb1dc6584352d4aaff882ad8fb91702d04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="outbytestring"></a>__outbytestring
**Блок, относящийся только к системам Майкрософт**  
  
 Приводит к возникновению ошибки `rep outsb` инструкции, которая отправляет первый `Count` байт данных, на который указывает `Buffer` для порта, указанного по `Port`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Port`  
 Порт для отправки данных.  
  
 [in] `Buffer`  
 Данные для отправки указанный порт.  
  
 [in] `Count`  
 Число байтов данных, отправляемых.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__outbytestring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта процедура доступна только как встроенная функция.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)