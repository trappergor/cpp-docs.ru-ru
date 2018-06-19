---
title: set_terminate (CRT) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- set_terminate
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
- set_terminate
dev_langs:
- C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e62dc1e4f99a1d2707c6e7b86c79e0ffc8aa027
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450980"
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

Устанавливает вашу собственную подпрограмму завершения, которая будет вызываться **завершить**.

## <a name="syntax"></a>Синтаксис

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Параметры

*termFunction*<br/>
Указатель на пользовательскую функцию завершения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию, зарегистрированные с **set_terminate** , чтобы можно было впоследствии восстановить предыдущую функцию. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **NULL**.

## <a name="remarks"></a>Примечания

**Set_terminate** функция устанавливает *termFunction* как функция, вызываемая с **завершить**. **set_terminate** используется с обработкой исключений C++ и может быть вызвана в любой момент в программе до исключения. **Завершение** вызовы [прервать](abort.md) по умолчанию. Это значение по умолчанию можно изменить, создав собственную функцию завершения и вызвав **set_terminate** с именем функции в качестве аргумента. **Завершение** вызывает последнюю функцию, заданную в качестве аргумента для **set_terminate**. После выполнения всех необходимых задач очистки *termFunction* должна завершить программу. Если он не существует (если она возвращает вызывающему), [прервать](abort.md) вызывается.

В многопоточной среде функции завершения поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции завершения. Таким образом, каждый поток отвечает за собственную обработку завершения.

**Terminate_function** определен тип обработки исключений. H как указатель на функцию завершения пользовательских *termFunction* , возвращающий **void**. Пользовательская функция *termFunction* может не иметь аргументов и не должен возвращать вызывающему. В этом случае [прервать](abort.md) вызывается. Исключение не может быть создано изнутри *termFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate** функция работает только вне отладчика.

Имеется один **set_terminate** обработчик для всех динамически связанных библиотек DLL или exe; даже при вызове **set_terminate** Ваш обработчик может быть заменен другим или вы можете заменить обработчик, заданный в другом Библиотеки DLL или EXE.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [terminate](terminate-crt.md).

## <a name="see-also"></a>См. также

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
