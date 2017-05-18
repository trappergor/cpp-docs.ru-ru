---
title: "_local_unwind2 | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
dev_langs:
- C++
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
caps.latest.revision: 5
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 72545cfe6520771838fd77c6e00910e31fcdf8b4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="localunwind2"></a>_local_unwind2
Внутренняя функция CRT. Выполняет все обработчики завершения, перечисленные в указанной таблице области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _local_unwind2(  
   PEXCEPTION_REGISTRATION xr,  
   int stop  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `xr`  
 Запись регистрации, которая связана с одной таблицей области.  
  
 [входной] `stop`  
 Лексический уровень, который указывает, где должна остановиться функция `_local_unwind2`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод используется только средой выполнения. Не вызывайте метод в коде.  
  
 Когда этот метод выполняет обработчики завершения, он начинает выполнение на текущем лексическом уровне и проходит все лексические уровни, пока не достигнет уровня, указанного параметром `stop`. Он не выполняет обработчики завершения на уровне, указанном параметром `stop`.  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
