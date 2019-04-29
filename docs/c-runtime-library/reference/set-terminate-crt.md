---
title: set_terminate (CRT)
ms.date: 11/04/2016
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
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 7be81dec7fba80a273d635cbd30b96b09928bc66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356450"
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

Возвращает указатель на предыдущую функцию, зарегистрированную с **set_terminate** таким образом, чтобы можно было впоследствии восстановить предыдущую функцию. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **NULL**.

## <a name="remarks"></a>Примечания

**Set_terminate** функция устанавливает *termFunction* как функция, вызываемая с **завершить**. **set_terminate** используется с C++ обработки исключений и может быть вызвана в любом месте программы, прежде чем возникает исключение. **завершить** вызовы [прервать](abort.md) по умолчанию. Это значение по умолчанию можно изменить, создав собственную функцию завершения и вызвав **set_terminate** с именем этой функции в качестве аргумента. **завершить** вызывает последнюю функцию, заданную в качестве аргумента для **set_terminate**. После выполнения всех необходимых задач очистки *termFunction* должна завершить программу. Если не существует (если он возвращает в вызывающий его объект), [прервать](abort.md) вызывается.

В многопоточной среде функции завершения поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции завершения. Таким образом, каждый поток отвечает за собственную обработку завершения.

**Terminate_function** определен тип обработки исключений. H как указатель на функцию завершения, определяемые пользователем *termFunction* , возвращающий **void**. Настраиваемой функции *termFunction* может не иметь аргументов и не должен возвращать его вызывающему. В этом случае [прервать](abort.md) вызывается. Исключение не может быть вызвано из функции *termFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate** функция работает только вне отладчика.

Будет только один **set_terminate** обработчика для всех динамически связанных библиотек DLL или exe; даже если вы вызываете **set_terminate** Ваш обработчик может быть заменен другим или вы можете заменить обработчик, заданный на другое Библиотеки DLL или EXE-файла.

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
