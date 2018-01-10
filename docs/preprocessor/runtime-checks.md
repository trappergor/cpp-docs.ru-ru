---
title: "runtime_checks | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
dev_langs: C++
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7bc333e539ba67b2a999bbeb5a08b9002da4e1fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimechecks"></a>runtime_checks
Отключает или восстанавливает параметры [/RTC](../build/reference/rtc-run-time-error-checks.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>Примечания  
 Невозможно включить проверку времени выполнения, не включенную с параметром компилятора. Например, если не указать параметры /RTC, указание `#pragma runtime_checks( "s", restore)` не приведет ко включению проверки кадра стека.  
  
 Директива pragma **runtime_checks** должна находиться за пределами функции; она вступает в силу в первой функции, определенной после этой директивы. Аргументы **restore** и **off** включают или отключают параметры, указанные в директиве *runtime_checks* .  
  
 Директива *runtime_checks* может содержать ноль или несколько параметров, приведенных в следующей таблице.  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>Параметры директивы pragma runtime_checks  
  
|Параметры|Тип проверки времени выполнения|  
|--------------------|-----------------------------|  
|**s**|Включает проверку (кадра) стека.|  
|**c**|Сообщает, когда значение назначается меньшему типу данных, что приводит к потере данных.|  
|**u**|Сообщает о том, что переменная используется до ее определения.|  
  
 Эти же буквы используются с параметром компилятора /RTC. Пример:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 Директива pragma **runtime_checks** с пустой строкой (**""**) представляет собой специальную форму директивы.  
  
-   При использовании параметра **off** она отключает проверки ошибок во время выполнения, перечисленные в таблице выше.  
  
-   При использовании параметра **restore** она сбрасывает проверки ошибок во время выполнения до указанных с помощью параметра компилятора /RTC.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
