---
title: __security_init_cookie | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84edc9fb461a6f0721abb648a88e1d81a4a19d07
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678961"
---
# <a name="securityinitcookie"></a>__security_init_cookie

Инициализирует глобальный cookie-файл безопасности.

## <a name="syntax"></a>Синтаксис

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Примечания

Глобальный cookie-файл безопасности используется для защиты от переполнения буфера в коде, скомпилированном с параметром [/GS (проверка безопасности буфера)](../../build/reference/gs-buffer-security-check.md), и в коде, в котором используется структурная обработка исключений. При входе в функцию с защитой от переполнения cookie-файл помещается в стек, а при выходе значение в стеке сравнивается с глобальным cookie-файлом. Любое различие между ними указывает, что произошло переполнение буфера, что приводит к немедленному завершению работы программы.

Как правило **__security_init_cookie** вызывается средой CRT при его инициализации. Если пропустить инициализацию CRT, например, если вы используете [/Entry](../../build/reference/entry-entry-point-symbol.md) для указания точки ввода, то нужно вызвать **__security_init_cookie** самостоятельно. Если **__security_init_cookie** не вызывается, глобальный файл cookie безопасности присвоено значение по умолчанию и нарушается защита от переполнения буфера. Так как злоумышленник может использовать это значение по умолчанию файл cookie, чтобы обойти проверку переполнения буфера, рекомендуется всегда вызывать **__security_init_cookie** при определении собственной точки входа.

Вызов **__security_init_cookie** необходимо вызывать до любой защищенную от переполнения вводе функции; в противном случае будет обнаружено ложное переполнение буфера. Подробнее: [Ошибка R6035 времени выполнения C](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Пример

Примеры см. в разделе [Ошибка R6035 времени выполнения C](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**__security_init_cookie** является расширением Майкрософт для стандартной библиотеки C времени выполнения. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Microsoft Security Response Center](https://www.microsoft.com/en-us/msrc?rtc=1)
