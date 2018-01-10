---
title: "feholdexcept2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs: C++
helpviewer_keywords: feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1455f3b963c2d9faf7c2e96a2d6684e0e412ef8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="feholdexcept"></a>feholdexcept
Сохраняет текущую среду с плавающей запятой в указанном объекте, очищает флаги состояний с плавающей запятой и, если это возможно, переводит среду с плавающей запятой в режим без остановки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `penv`  
 Указатель на объект `fenv_t`, содержащий копию среды с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль только в том случае, если функция является возможность успешного включения обработки исключений с плавающей запятой без остановки.  
  
## <a name="remarks"></a>Примечания  
 Функция `feholdexcept` используется для сохранения состояния текущей среды с плавающей запятой в объект `fenv_t`, на который указывает `penv`, и настройки среды таким образом, чтобы при возникновении исключений с плавающей запятой выполнение не прерывалось. Это называется режимом без остановки.  В этом режиме работа продолжается, пока среда не будет восстановлена с помощью функции [fesetenv](fesetenv1.md) или [feupdateenv](../../c-runtime-library/reference/feupdateenv.md).  
  
 Эту функцию можно использовать в начале подпрограммы, который должна скрывать от вызывающей стороны одно или несколько исключений с плавающей запятой. Чтобы сообщить об исключении, можно просто удалить нежелательные исключения с помощью функции [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md), а затем завершить режим без остановки, вызвав `feupdateenv`.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`feholdexcept`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](fesetenv1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)