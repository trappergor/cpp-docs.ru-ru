---
title: "longjmp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- longjmp
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
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b5af03e83cc39c20fca310ba0c2377469c59ef38
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="longjmp"></a>longjmp
Восстанавливает среду стека и языковой стандарт выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `env`  
 Переменная, в которой хранится среда.  
  
 *value*  
 Значение, возвращаемое в вызов `setjmp`.  
  
## <a name="remarks"></a>Примечания  
 Функция `longjmp` восстанавливает среду стека и языковой стандарт выполнения, которые ранее были сохранены в параметре `env` функцией `setjmp`. Функции `setjmp` и `longjmp` являются одним из способов выполнить нелокальный вызов `goto`. Обычно они используются для передачи управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования обычных соглашений вызова и возврата.  
  
 Вызов функции `setjmp` сохраняет текущую среду стека в параметре `env`. Последующий вызов функции `longjmp` восстанавливает сохраненную среду и возвращает управление в точку, следующую сразу за соответствующим вызовом функции `setjmp`. Выполнение возобновляется так, как если бы параметр *value* был только что возвращен в результате вызова функции `setjmp`. Все переменные (за исключением регистровых переменных), доступные для получившей управление подпрограммы, содержат те значения, которые они имели при вызове функции `longjmp`. Значения регистровых переменных непредсказуемы. Значение, возвращаемое функцией `setjmp`, должно быть ненулевым. Если переданный параметр *value* равен 0, фактическое возвращаемое значение будет равно 1.  
  
 Функцию `longjmp` необходимо вызывать до возврата функции, которая вызвала `setjmp`, иначе результаты будут непредсказуемыми.  
  
 При использовании функции `longjmp` соблюдайте следующие ограничения:  
  
-   Не рассчитывайте на то, что значения регистровых переменных останутся теми же. Значения регистровых переменных, установленные на момент вызова подпрограммы `setjmp`, после вызова `longjmp` могут измениться.  
  
-   Не используйте функцию `longjmp` для передачи управления из подпрограммы обработки прерываний, если прерывание не вызвано с исключением вычислений с плавающей запятой. В этом случае программа может выполнять возврат из обработчика прерываний посредством функции `longjmp`, если она сначала повторно инициализирует пакет вычислений с плавающей запятой путем вызова функции `_fpreset`.  
  
     **Примечание.** Будьте внимательны при использовании функций `setjmp` и `longjmp` в программах на C++. Так как эти функции не поддерживают семантику объектов C++, лучше использовать механизм обработки исключений C++.  
  
 Дополнительные сведения см. в разделе [Использование setjmp и longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`longjmp`|\<setjmp.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример для [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)
