---
title: __security_init_cookie
ms.date: 11/04/2016
api_name:
- __security_init_cookie
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- security_init_cookie
- __security_init_cookie
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
ms.openlocfilehash: 9f7e9924f4a96803749418d777e5ee2020f9df78
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948720"
---
# <a name="__security_init_cookie"></a>__security_init_cookie

Инициализирует глобальный cookie-файл безопасности.

## <a name="syntax"></a>Синтаксис

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Примечания

Глобальный cookie-файл безопасности используется для защиты от переполнения буфера в коде, скомпилированном с параметром [/GS (проверка безопасности буфера)](../../build/reference/gs-buffer-security-check.md), и в коде, в котором используется структурная обработка исключений. При входе в функцию с защитой от переполнения cookie-файл помещается в стек, а при выходе значение в стеке сравнивается с глобальным cookie-файлом. Любое различие между ними указывает, что произошло переполнение буфера, что приводит к немедленному завершению работы программы.

Обычно **__security_init_cookie** вызывается CRT при инициализации. Если обойти инициализацию CRT — например, если вы используете [/entry](../../build/reference/entry-entry-point-symbol.md) для указания точки входа, то необходимо вызвать **__security_init_cookie** самостоятельно. Если **__security_init_cookie** не вызывается, для глобального файла cookie безопасности задается значение по умолчанию, и защита от переполнения буфера будет скомпрометирована. Так как злоумышленник может воспользоваться этим значением файла cookie по умолчанию, чтобы отменить проверку переполнения буфера, рекомендуется всегда вызывать **__security_init_cookie** при определении собственной точки входа.

Вызов **__security_init_cookie** должен быть выполнен до того, как будет указана любая функция, защищенная с помощью переполнения. в противном случае будет обнаружено ложное переполнение буфера. Подробнее: [Ошибка R6035 времени выполнения C](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Пример

Примеры см. в разделе [Ошибка R6035 времени выполнения C](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**__security_init_cookie** — это расширение Майкрософт для стандартной библиотеки времени выполнения C. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Центр Microsoft Security Response Center](https://www.microsoft.com/msrc?rtc=1)
