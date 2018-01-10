---
title: "___setlc_active_func, ___unguarded_readlc_active_add_func | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
dev_langs: C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a1ecc14403a7a08fed73fb10f15dd25051b0a28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func, ___unguarded_readlc_active_add_func
УСТАРЕВШИЕ. Среда CRT экспортирует эти внутренние функции только для поддержания совместимости с двоичными данными.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int ___setlc_active_func(void);  
int * ___unguarded_readlc_active_add_func(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не важно.  
  
## <a name="remarks"></a>Примечания  
 Хотя внутренние функции CRT `___setlc_active_func` и `___unguarded_readlc_active_add_func` являются устаревшими и более не используются, они экспортируются библиотекой CRT для поддержания совместимости с двоичными данными. Изначальной целью функции `___setlc_active_func` был возврат числа текущих активных вызовов функции `setlocale`. Изначальной целью функции `___unguarded_readlc_active_add_func` был возврат числа функций, которые ссылаются на языковой стандарт, не блокируя его.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|Нет|  
  
## <a name="see-also"></a>См. также  
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)