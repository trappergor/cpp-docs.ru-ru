---
title: "fegetenv1 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: fetegenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetenv
- fenv/fegetenv
dev_langs: C++
helpviewer_keywords: fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3da1a5837a2c2e3a2cd1c7987363b251bc67b567
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fegetenv"></a>fegetenv
Сохраняет текущую среду с плавающей запятой в указанном объекте.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `penv`  
 Указатель на объект `fenv_t`, содержащий текущие значения среды с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0, если среда с плавающей запятой успешно сохранена в `penv`. В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Затем функция `fegetenv` задает текущую среду с плавающей запятой в объекте, указанном с помощью функции `penv`. Среда с плавающей запятой представляет собой набор флагов состояний и режимов управления, влияющих на вычисления с плавающей запятой. Включает режим направления округления и флаги состояния для исключений с плавающей запятой.  Если `penv` не указывает на допустимый объект `fenv_t`, последующее поведение функции будет неопределенным.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fegetenv`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)