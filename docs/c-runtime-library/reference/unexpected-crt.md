---
title: unexpected (CRT) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- unexpected
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
- unexpected
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8dc51c41ebf938f59493cbd62fac3e0a491601
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408111"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

Вызовы **завершить** или функцию, заданную с помощью **set_unexpected**.

## <a name="syntax"></a>Синтаксис

```C
void unexpected( void );
```

## <a name="remarks"></a>Примечания

**Непредвиденная** не используется в текущей реализации обработки исключений C++. **Непредвиденная** вызовы **завершить** по умолчанию. Это поведение по умолчанию можно изменить, создав функцию пользовательского завершения и вызвав **set_unexpected** с именем функции в качестве аргумента. **Непредвиденная** вызывает последнюю функцию, заданную в качестве аргумента для **set_unexpected**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**unexpected**|\<eh.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
