---
title: "PogoSafeMode | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f40dad6feff9e49deeb495e8acbf2584dea3e41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pogosafemode"></a>PogoSafeMode
Укажите, следует ли использовать быстром режиме или безопасном режиме для профилирования приложений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>Примечания  
 Профильная оптимизация (PGO) имеет два возможных режима во время фазы профилирования: быстрый и безопасный режим. При профилировании в быстром режиме, она использует **INC** инструкции для увеличения счетчиков данных. **INC** инструкция выполняется быстрее, но не является потокобезопасной. При профилировании в безопасном режиме, она использует **LOCK INC** инструкции для увеличения счетчиков данных. **LOCK INC** инструкция имеет ту же функциональность, что **INC** инструкция имеет и является потокобезопасной, но работает медленнее, чем **INC** инструкции.  
  
 По умолчанию профилирование вероятностного Оптимизатора работает в быстром режиме. `PogoSafeMode`— требуется, только если вы хотите использовать безопасный режим.  
  
 Чтобы выполнить профилирование вероятностного Оптимизатора в безопасном режиме, необходимо использовать переменную среды `PogoSafeMode` или параметр компоновщика **- PogoSafeMode**, в зависимости от системы. Если вы выполняете профилирование на x64 компьютера, необходимо использовать параметр компоновщика. Если вы выполняете профилирование на x86 компьютера, необходимо определить переменную среды любое значение перед началом процесса оптимизации.  
  
## <a name="example"></a>Пример  
  
```  
set PogoSafeMode=1  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)