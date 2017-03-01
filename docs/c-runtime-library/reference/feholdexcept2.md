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
apiname:
- feholdexcept
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
dev_langs:
- C++
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 40c56f3ebd01ac809b48c48dcda85ef8a3217be4
ms.lasthandoff: 02/24/2017

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
 Возвращает ноль только в том случае, если функция способна успешно включить непрерывную обработку исключений с плавающей запятой.  
  
## <a name="remarks"></a>Примечания  
 Функция `feholdexcept` используется для сохранения состояния текущей среды с плавающей запятой в объект `fenv_t`, на который указывает `penv`, и настройки среды таким образом, чтобы при возникновении исключений с плавающей запятой выполнение не прерывалось. Это называется режимом без остановки.  В этом режиме работа продолжается, пока среда не будет восстановлена с помощью функции [fesetenv](http://msdn.microsoft.com/Library/a34b2705-0bd4-452e-a30f-eea3898d8183) или [feupdateenv](../../c-runtime-library/reference/feupdateenv.md).  
  
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
 [fesetenv](http://msdn.microsoft.com/Library/a34b2705-0bd4-452e-a30f-eea3898d8183)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)
