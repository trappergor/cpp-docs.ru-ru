---
title: "Константы spawn | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
dev_langs:
- C++
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 89b430cf7e64d64137cd5f844573d0fe5a3a3bc7
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="spawn-constants"></a>Константы spawn
## <a name="syntax"></a>Синтаксис  
  
```  
#include <process.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Аргумент `mode` определяет действие, предпринимаемое процессом перед операцией инициализации и в течение нее. Для `mode` возможны следующие значения:  
  
|Константа|Значение|  
|--------------|-------------|  
|`_P_OVERLAY`|Перекрывает вызывающий процесс новым процессом, уничтожая вызывающий процесс (тот же эффект, что и у вызовов функции `_exec`).|  
|`_P_WAIT`|Приостанавливает вызывающий поток до тех пор, пока не будет завершено выполнение нового процесса (синхронная функция `_spawn`).|  
|`_P_NOWAIT`, `_P_NOWAITO`|Продолжает выполнять вызывающий процесс параллельно с новым процессом (асинхронная функция `_spawn`).|  
|`_P_DETACH`|Продолжает выполнять вызывающий процесс; новый процесс выполняется в фоновом режиме без доступа к консоли или клавиатуре. Вызовы функции `_cwait` для нового процесса будут завершаться с ошибкой. Это асинхронная функция `_spawn`.|  
  
## <a name="see-also"></a>См. также  
 [Функции _spawn, _wspawn](../c-runtime-library/spawn-wspawn-functions.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)
