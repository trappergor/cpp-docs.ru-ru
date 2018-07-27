---
title: set_unexpected (CRT) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7af5cce0b17747beb8c136f75489025d741f864a
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451879"
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

Устанавливает собственную функцию завершения, которая будет вызываться **unexpected**.

## <a name="syntax"></a>Синтаксис

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Параметры

*unexpFunction*<br/>
Указатель на функцию, который пишется для замены **Непредвиденная** функции.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию завершения, зарегистрированные с **_set_unexpected** , чтобы можно было впоследствии восстановить предыдущую функцию. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **NULL**.

## <a name="remarks"></a>Примечания

**Set_unexpected** функция устанавливает *unexpFunction* как функция, вызываемая с **Непредвиденная**. **Непредвиденная** не используется в текущей реализации обработки исключений C++. **Unexpected_function** определен тип обработки исключений. H как указатель на определяемые пользователем функции Непредвиденная *unexpFunction* , возвращающий **void**. Пользовательскую *unexpFunction* функция не должна возвращать вызывающему объекту.

```cpp
typedef void ( *unexpected_function )( );
```

По умолчанию **Непредвиденная** вызовы **завершить**. Это поведение по умолчанию можно изменить, создав собственную функцию завершения и вызвав **set_unexpected** с именем функции в качестве аргумента. **Непредвиденная** вызывает последнюю функцию, заданную в качестве аргумента для **set_unexpected**.

В отличие от завершения пользовательские функции, установленные путем вызова **set_terminate**, исключение изнутри *unexpFunction*.

В многопоточной среде непредвиденные функции поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной непредвиденной функции. Таким образом, каждый поток отвечает за собственную обработку непредвиденных функций.

В текущей реализации обработки исключений C++, корпорация Майкрософт **Непредвиденная** вызовы **завершить** по умолчанию и никогда не вызывается из библиотеки времени выполнения обработки исключений. Нет определенного вызова не дает преимуществ **Непредвиденная** вместо **завершить**.

Имеется один **set_unexpected** обработчик для всех динамически связанных библиотек DLL или exe; даже при вызове **set_unexpected** Ваш обработчик может быть заменен другим или вы можете непроизвольно заменить обработчик, заданный библиотеки DLL или EXE.

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
