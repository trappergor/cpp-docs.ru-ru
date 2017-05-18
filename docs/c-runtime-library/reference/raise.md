---
title: "raise | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- raise
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
- Raise
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
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
ms.openlocfilehash: 9cfcedc524b94d0aa6c381416c445cf62f9cf2fb
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="raise"></a>raise
Отправляет сигнал выполняемой программе.  
  
> [!NOTE]
>  Не используйте этот метод для завершения приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки. Закрытие приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] программным способом или с помощью пользовательского интерфейса не допускается в соответствии с разделом 3.6 [сертификационных требований к приложениям для Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889). Дополнительные сведения см. в разделе [Жизненный цикл приложений (приложения для Магазина Windows)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *sig*  
 Сигнал, который требуется инициализировать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха **raise** возвращает 0. В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Примечания  
 Функция **raise** отправляет сигнал *sig* выполняемой программе. Если предыдущий вызов **signal** установил функцию обработки сигнала для *sig*, **raise** выполняет эту функцию. Если функция обработчика не была установлена, то выполняется действие по умолчанию, связанное со значением сигнала *sig*, как показано ниже.  
  
|Signal|Значение|Default|  
|------------|-------------|-------------|  
|`SIGABRT`|Аварийное завершение|Завершает вызывающую программу с кодом выхода 3|  
|`SIGFPE`|Ошибка с плавающей запятой|Завершает вызывающую программу|  
|`SIGILL`|Недопустимая инструкция|Завершает вызывающую программу|  
|`SIGINT`|Прерывание CTRL+C|Завершает вызывающую программу|  
|`SIGSEGV`|Недопустимый класс хранения|Завершает вызывающую программу|  
|`SIGTERM`|Запрос на прекращение, отправленный в программу|Игнорирует сигнал|  
  
 Если аргумент не является допустимым сигналом, как указано выше, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если ошибка не обработана, функция задает для параметра `errno` значение `EINVAL` и возвращает ненулевое значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|**raise**|\<signal.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)
