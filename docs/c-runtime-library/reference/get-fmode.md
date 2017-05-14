---
title: "_get_fmode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_fmode
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_fmode
- _get_fmode
dev_langs:
- C++
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
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
ms.openlocfilehash: 3081981cde81b200d5896bab4d362db13742eb42
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="getfmode"></a>_get_fmode
Получает режим преобразования файла по умолчанию для операций файлового ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pmode`  
 Указатель на целое число, в которое должно быть подставлено значение режима по умолчанию: `_O_TEXT` или `_O_BINARY`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае ошибки. Если параметр `pmode` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция возвращает значение [_fmode](../../c-runtime-library/fmode.md) глобальной переменной. Эта переменная определяет режим преобразования файла по умолчанию для потоков операций низкоуровневого и файлового ввода-вывода, таких как `_open`, `_pipe`, `fopen` и `freopen`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_get_fmode`|\<stdlib.h>|\<fcntl.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример в разделе [_set_fmode](../../c-runtime-library/reference/set-fmode.md).  
  
## <a name="see-also"></a>См. также  
 [_fmode](../../c-runtime-library/fmode.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md)
