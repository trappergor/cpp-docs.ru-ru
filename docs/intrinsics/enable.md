---
title: "_Включить | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _enable
- _enable_cpp
dev_langs: C++
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d8e0f6ac28bb24b81f396cac9251f9ffeccf157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="enable"></a>_enable
**Блок, относящийся только к системам Microsoft**  
  
 Позволяет прерывания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _enable(void);  
```  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_enable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 `_enable`Указывает, что обработчик установить флаг прерывания. На платформе x86 систем, эта функция создает инструкцию установить флаг прерывания (`sti`) .  
  
 Эта функция доступна только в режиме ядра. При использовании в пользовательском режиме, исключение привилегированной инструкции отбрасывается.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)