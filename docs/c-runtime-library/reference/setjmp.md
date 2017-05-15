---
title: "setjmp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setjmp
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
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 602ed9f5b1ff3c809055d9a231f81ee649bab8e8
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="setjmp"></a>setjmp
Сохраняет текущее состояние программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `env`  
 Переменная, в которой хранится среда.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0 после сохранения среды стека. Если функция `setjmp` возвращается в результате вызова функции `longjmp`, она возвращает аргумент `value` функции `longjmp`, или, если аргумент `value` функции `longjmp` равен 0, функция `setjmp` возвращает 1. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 Функция `setjmp` сохраняет среду стека, которую можно впоследствии восстановить с помощью функции `longjmp`. При совместном использовании функции `setjmp` и `longjmp` предоставляют способ выполнения нелокального `goto`. Обычно они используются для передачи управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования обычных соглашений вызова или возврата.  
  
 Вызов функции `setjmp` сохраняет текущую среду стека в параметре `env`. Последующий вызов функции `longjmp` восстанавливает сохраненную среду и возвращает управление в точку, следующую сразу за соответствующим вызовом функции `setjmp`. Все переменные (за исключением регистровых переменных), доступные для получившей управление подпрограммы, содержат те значения, которые они имели при вызове функции `longjmp`.  
  
 Функцию `setjmp` невозможно использовать для перехода из машинного кода в управляемый.  
  
 **Примечание.** Функции `setjmp` и `longjmp` не поддерживают семантику объекта C++. В программах на C++ используйте механизм обработки исключений C++.  
  
 Дополнительные сведения см. в разделе [Использование setjmp и longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`setjmp`|\<setjmp.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [_setjmp3](../../c-runtime-library/setjmp3.md)
