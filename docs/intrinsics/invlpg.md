---
title: __invlpg | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5a25e16439673f367cfe0bfe208dbc21a621b81
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540692"
---
# <a name="invlpg"></a>__invlpg
**Блок, относящийся только к системам Microsoft**  
  
 Создает x86 `invlpg` инструкции, что делает недействительным буфера ассоциативной трансляции (TLB) для страницы, связанные с объемом памяти, на которые указывают `Address`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in]  `Address`  
 64-разрядный адрес.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__invlpg`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Встроенная `__invlpg` выдает привилегированной инструкции и доступна только в режиме ядра с уровнем привилегий (CPL) 0.  
  
 Эта процедура доступна только как встроенная функция.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)