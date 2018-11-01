---
title: set_unexpected (CRT)
ms.date: 11/04/2016
apiname:
- set_unexpected
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
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 6c38421e447ca7b3f263148f51f0ade5c59e2804
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484231"
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

Устанавливает собственную функцию завершения, которая будет вызываться **unexpected**.

## <a name="syntax"></a>Синтаксис

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Параметры

*unexpFunction*<br/>
Указатель на функцию, которая заменит **Непредвиденная** функции.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию завершения, зарегистрированную с помощью **_set_unexpected** таким образом, чтобы можно было впоследствии восстановить предыдущую функцию. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **NULL**.

## <a name="remarks"></a>Примечания

**Set_unexpected** функция устанавливает *unexpFunction* как функция, вызываемая с **Непредвиденная**. **Непредвиденная** не используется в текущей реализации обработки исключений C++. **Unexpected_function** определен тип обработки исключений. H как указатель на определенную пользователем непредвиденную функцию, *unexpFunction* , возвращающий **void**. Пользовательский *unexpFunction* функция не должна возвращать его вызывающему.

```cpp
typedef void ( *unexpected_function )( );
```

По умолчанию **Непредвиденная** вызовы **завершить**. Это поведение по умолчанию можно изменить, создав собственную функцию завершения и вызвав **set_unexpected** с именем этой функции в качестве аргумента. **Непредвиденная** вызывает последнюю функцию, заданную в качестве аргумента для **set_unexpected**.

В отличие от пользовательской функции завершения установки с помощью вызова **set_terminate**, исключение может создаваться изнутри *unexpFunction*.

В многопоточной среде непредвиденные функции поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной непредвиденной функции. Таким образом, каждый поток отвечает за собственную обработку непредвиденных функций.

В текущей реализации обработки исключений C++, Microsoft **Непредвиденная** вызовы **завершить** по умолчанию и никогда не вызывается из библиотеки времени выполнения обработки исключений. Нет никаких особых преимуществ вызова **Непредвиденная** вместо **завершить**.

Будет только один **set_unexpected** обработчика для всех динамически связанных библиотек DLL или exe; даже если вы вызываете **set_unexpected** Ваш обработчик может быть заменен другим или вы можете непроизвольно заменить обработчик, установленный библиотеки DLL или EXE-файла.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
