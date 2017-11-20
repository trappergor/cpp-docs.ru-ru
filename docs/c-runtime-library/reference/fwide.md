---
title: "fwide | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fwide
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords: fwide
dev_langs: C++
helpviewer_keywords: fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f10bd98a6dedba2181aa1d5ebba60f64dda093be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fwide"></a>fwide
Не реализовано.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` (игнорируется).  
  
 `mode`  
 Новая ширина потока: положительное значение для расширенных символов, отрицательное для байта, ноль, чтобы оставить без изменений. (Это значение игнорируется.)  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта функция в настоящее время просто возвращает `mode`.  
  
## <a name="remarks"></a>Примечания  
 Текущая версия этой функции не соответствует стандарту.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fwide`|\<wchar.h>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).