---
title: "_setjmp3 | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs: C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba68e059224d2d15046730a9ee0058e3114d52ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setjmp3"></a>_setjmp3
Внутренняя функция CRT. Новая реализация функции `setjmp`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _setjmp3(  
   OUT jmp_buf env,  
   int count,  
   (optional parameters)  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `env`  
 Адрес буфера для хранения сведений о состоянии.  
  
 [входной] `count`  
 Число дополнительных `DWORD` данных, хранимых в `optional parameters`.  
  
 [входной] `optional parameters`  
 Дополнительные данные, отправленные встроенной функцией `setjmp`. Первое `DWORD` — это указатель функции, которая используется для очистки лишних данных и возврата к состоянию неизменяемого регистра. Второе `DWORD` — уровень повторной попытки, который необходимо восстановить. Все дальнейшие данные сохраняются в массиве универсальных данных в `jmp_buf`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
## <a name="remarks"></a>Примечания  
 Не используйте эту функцию в программе C++. Это встроенная функция, не поддерживающая C++. Дополнительные сведения об использовании `setjmp` см. в статье [Using setjmp/longjmp](../cpp/using-setjmp-longjmp.md) (Использование setjmp и longjmp).  
  
## <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)