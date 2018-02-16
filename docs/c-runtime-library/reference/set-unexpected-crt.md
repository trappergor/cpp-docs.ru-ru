---
title: "set_unexpected (CRT) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- set_unexpected
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
- set_unexpected
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: edc1d3b96ee5b52d349b30434932d2c9770267b4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)
Устанавливает собственную функцию завершения, которая будет вызываться `unexpected`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `unexpFunction`  
 Указатель на пользовательскую функцию, которая заменит функцию `unexpected`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на предыдущую функцию завершения, зарегистрированную с помощью `_set_unexpected`, чтобы предыдущую функцию можно было впоследствии восстановить. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## <a name="remarks"></a>Примечания  
 Функция `set_unexpected` устанавливает `unexpFunction` как функцию, вызываемую функцией `unexpected`. `unexpected` не используется в текущей реализации обработчика исключений C++. Тип `unexpected_function` определен в файле EH.H как указатель на определенную пользователем непредвиденную функцию, `unexpFunction`, возвращающую значение `void`. Пользовательская функция `unexpFunction` не должна возвращать управление вызвавшему ее объекту.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 По умолчанию `unexpected` вызывает функцию `terminate`. Это поведение по умолчанию можно изменить, создав собственную функцию завершения и вызвав функцию `set_unexpected` с именем этой функции в качестве аргумента. `unexpected` вызывает последнюю функцию, заданную в качестве аргумента для функции `set_unexpected`.  
  
 В отличие от пользовательской функции завершения, установленной с помощью вызова `set_terminate`, исключение может быть вызвано из функции `unexpFunction`.  
  
 В многопоточной среде непредвиденные функции поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной непредвиденной функции. Таким образом, каждый поток отвечает за собственную обработку непредвиденных функций.  
  
 В текущей реализации обработчика исключений C++ Майкрософт `unexpected` вызывает `terminate` по умолчанию и никогда не вызывается из библиотеки времени выполнения для обработки исключений. Вызов функции `unexpected` не обеспечивает никаких особых преимуществ по сравнению с вызовом функции `terminate`.  
  
 Существует только один обработчик `set_unexpected` для всех динамически связанных файлов DLL или EXE; даже если вы вызвали функцию `set_unexpected`, ваш обработчик может быть заменен другим или вы можете заменить обработчик, заданный другими файлами DLL или EXE.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`set_unexpected`|\<eh.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)