---
title: "Константы действия signal | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs: C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 26a5b349836b7c9b08a66d4df8f3d2bedbe5b63f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="signal-action-constants"></a>Константы действий signal
Действие, выполняемое при получении сигнала прерывания, зависит от значения `func`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Аргумент `func` должен содержать адрес функции или одну из констант манифеста, определенных в SIGNAL.H (перечислены ниже).  
  
 `SIG_DFL`  
 Использует ответ системы по умолчанию. Если вызывающая программа использует потоковый ввод-вывод, созданные библиотекой времени выполнения буферы не очищаются.  
  
 `SIG_IGN`  
 Игнорирует сигнал прерывания. Это значение нельзя использовать для `SIGFPE`, так как в этом случае состояние процесса с плавающей запятой остается неопределенным.  
  
 `SIG_SGE`  
 Указывает, что в signal произошла ошибка.  
  
 `SIG_ACK`  
 Указывает, что было получено подтверждение.  
  
 `SIG_ERR`  
 Тип значения, возвращаемого из signal с информацией о произошедшей ошибке.  
  
## <a name="see-also"></a>См. также  
 [signal](../c-runtime-library/reference/signal.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)