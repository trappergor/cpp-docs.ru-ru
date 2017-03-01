---
title: "fesetenv1 | Документы Майкрософт"
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
- fesetenv
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
- fesetenv
- fenv/fesetenv
dev_langs:
- C++
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
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
ms.openlocfilehash: 40e20a2c6a3f3c22b9206ce078146b44bb841f68
ms.lasthandoff: 02/24/2017

---
# <a name="fesetenv"></a>fesetenv
Задает текущую среду с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `penv`  
 Указатель на объект `fenv_t`, который содержит среду вычислений с плавающей запятой, установленную вызовом функции [fegetenv](http://msdn.microsoft.com/Library/61df848d-6ba8-4c6e-be35-216436fe7736) или [feholdexcept](http://msdn.microsoft.com/Library/c286ace3-ec39-482a-be8b-f998d31003d9). Кроме того, вы можете указать запускаемую по умолчанию среду вычислений с плавающей запятой с помощью макроса FE_DFL_ENV.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0, если среда был успешно установлена.        В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Затем функция `fesetenv` задает текущую среду вычислений с плавающей запятой на основе значения, сохраненного в объекте `fenv_t`, на который указывает `penv`. Среда с плавающей запятой представляет собой набор флагов состояний и режимов управления, влияющих на вычисления с плавающей запятой. Включает режим округления и флаги состояния для исключений с плавающей запятой.  Если `penv` не задается с помощью макроса FE_DFL_ENV или не указывает на допустимый объект `fenv_t`, последующее поведение функции будет неопределенным.  
  
 Вызов этой функции задает флаги состояния исключений, которые находятся в объекте `penv`, но не вызывает эти исключения.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fesetenv`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)
