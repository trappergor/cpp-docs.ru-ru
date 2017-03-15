---
title: "feupdateenv | Документы Майкрософт"
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
- feupdateenv
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
apitype: HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
dev_langs:
- C++
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: 3
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
ms.openlocfilehash: 170e385a5741ced5612c060a7a537a05b4668432
ms.lasthandoff: 02/24/2017

---
# <a name="feupdateenv"></a>feupdateenv
Сохраняет вызванные в данный момент исключения с плавающей запятой, восстанавливает указанное состояние среды вычислений с плавающей запятой, после чего вызывает сохраненные исключения с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `penv`  
 Указатель на объект `fenv_t`, который содержит среду вычислений с плавающей запятой, установленную вызовом функции [fegetenv](http://msdn.microsoft.com/Library/61df848d-6ba8-4c6e-be35-216436fe7736) или [feholdexcept](http://msdn.microsoft.com/Library/c286ace3-ec39-482a-be8b-f998d31003d9). Кроме того, вы можете указать запускаемую по умолчанию среду вычислений с плавающей запятой с помощью макроса FE_DFL_ENV.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если все действия успешно завершены, возвращает 0.        В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Функция `feupdateenv` выполняет несколько действий. Сначала она автоматически сохраняет вызванные на данный момент флаги состояний исключения с плавающей запятой. Затем эта функция задает текущую среду вычислений с плавающей запятой на основе значения, сохраненного в объекте `fenv_t`, на который указывает `penv`. Если `penv` не задается с помощью макроса FE_DFL_ENV или не указывает на допустимый объект `fenv_t`, последующее поведение функции будет неопределенным. После этого функция `feupdateenv` вызывает локально сохраненные исключения с плавающей запятой.  
  
 Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`feupdateenv`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)
