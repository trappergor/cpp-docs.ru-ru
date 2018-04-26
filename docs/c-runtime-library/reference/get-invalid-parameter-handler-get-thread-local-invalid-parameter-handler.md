---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a3e4df593e027c77909f6d3d1ea7c7a106799a9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

Получает функцию, которая вызывается, когда CRT обнаруживает недопустимый аргумент.

## <a name="syntax"></a>Синтаксис

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на установленную в данный момент функцию обработчика недопустимого параметра или указатель NULL, если такая функция не задана.

## <a name="remarks"></a>Примечания

**_Get_invalid_parameter_handler** функция возвращает текущее обработчик глобального недопустимого параметра. Если глобальный обработчик недопустимого параметра не задан, возвращается указатель NULL. Аналогичным образом **_get_thread_local_invalid_parameter_handler** возвращает текущий обработчик недопустимого параметра локального потока вызывается для потока, или указатель null, если обработчик не был задан. Дополнительные сведения об установке глобального и локального для потока обработчика недопустимого параметра см. в разделе [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

Возвращаемый указатель на функцию обработчика недопустимого параметра имеет следующий тип:

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

Дополнительные сведения об обработчике недопустимого параметра см. в описании прототипа в разделе [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> или \<stdlib.h>|

**_Get_invalid_parameter_handler** и **_get_thread_local_invalid_parameter_handler** функции — только к системам Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Версии функций CRT повышенной безопасности](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
