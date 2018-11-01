---
title: unexpected (CRT)
ms.date: 11/04/2016
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
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 78538c0a10e183e72c742b041b297275c0859a03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534030"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

Вызовы **завершить** или функцию, заданную с помощью **set_unexpected**.

## <a name="syntax"></a>Синтаксис

```C
void unexpected( void );
```

## <a name="remarks"></a>Примечания

**Непредвиденная** не используется в текущей реализации обработки исключений C++. **Непредвиденная** вызовы **завершить** по умолчанию. Это поведение по умолчанию можно изменить, создав пользовательской функции завершения и вызвав **set_unexpected** с именем этой функции в качестве аргумента. **Непредвиденная** вызывает последнюю функцию, заданную в качестве аргумента для **set_unexpected**.

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
