---
title: "_CrtDbgBreak | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDbgBreak
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
f1_keywords:
- _CrtDbgBreak
- CrtDbgBreak
dev_langs:
- C++
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 105b86a3c06c17bd9d24ff6cedb213abf06dadcd
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgbreak"></a>_CrtDbgBreak
Устанавливает точку останова в определенной строке кода. (Используется только в режиме отладки.)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _CrtDbgBreak( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение отсутствует.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtDbgBreak` задает точку останова отладки в той строке кода, где находится функция. Она используется только в режиме отладки и зависит от определенного ранее параметра `_DEBUG`.  
  
 Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Запись собственных функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDbgBreak`|\<CRTDBG.h>|  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [__debugbreak](../../intrinsics/debugbreak.md)
