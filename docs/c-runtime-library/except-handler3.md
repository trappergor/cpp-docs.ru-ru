---
title: _except_handler3 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8253db3ce5a1ec60001bb32b241bfebe000502
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389411"
---
# <a name="excepthandler3"></a>_except_handler3
Внутренняя функция CRT. Используется платформой для поиска подходящего обработчика исключений для обработки текущего исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _except_handler3(  
   PEXCEPTION_RECORD exception_record,  
   PEXCEPTION_REGISTRATION registration,  
   PCONTEXT context,  
   PEXCEPTION_REGISTRATION dispatcher  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `exception_record`  
 Сведения о конкретном исключении.  
  
 [in] `registration`  
 Запись, которая указывает, какую таблицу области следует использовать для поиска обработчика исключений.  
  
 [in] `context`  
 Зарезервировано.  
  
 [in] `dispatcher`  
 Зарезервировано.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если исключение должно быть отброшено, возвращает значение `DISPOSITION_DISMISS`. Если исключение должно быть передано на уровень вверх в инкапсулируемые обработчики исключений, возвращает значение `DISPOSITION_CONTINUE_SEARCH`.  
  
## <a name="remarks"></a>Примечания  
 Если этот метод находит подходящий обработчик исключений, он передает исключение в обработчик. В этой ситуации метод не возвращается к вызвавшему его коду, и возвращаемое значение несущественно.  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)