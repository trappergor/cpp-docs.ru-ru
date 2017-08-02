---
title: "_lock | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lock
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- lock
- _lock
dev_langs:
- C++
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 41c7769cb2cd2c806e82ee2bd71fe027aa846151
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="lock"></a>_lock
Получает многопоточную блокировку.  
  
> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `locknum`  
 Идентификатор блокировки, которую нужно получить.  
  
## <a name="remarks"></a>Примечания  
 Если блокировка уже была получена, этот метод все равно получает блокировку и вызывает внутреннюю ошибку среды выполнения языка C (CRT). Если метод не может получить блокировку, он завершается с неустранимой ошибкой и устанавливает код ошибки `_RT_LOCK`.  
  
## <a name="requirements"></a>Требования  
 **Источник:** mlock.c  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_unlock](../c-runtime-library/unlock.md)
