---
title: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
dev_langs:
- C++
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9a6ea61883e6ce94bc41f16e7139156c68c8059
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082096"
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function

Управляет подпрограммами, которые должны вызываться во время выхода.

## <a name="syntax"></a>Синтаксис

```
int _initialize_onexit_table(
    _onexit_table_t* table
    );

int _register_onexit_function(
    _onexit_table_t* table,
    _onexit_t        function
    );

int _execute_onexit_table(
    _onexit_table_t* table
    );
```

#### <a name="parameters"></a>Параметры

*table*<br/>
[in, out] Указатель на таблицу функций onexit.

*function*<br/>
[in] Указатель на функцию, которую необходимо добавить в таблицу функций onexit.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает 0. В противном случае возвращает отрицательное значение.

## <a name="remarks"></a>Примечания

Эти функции представляют собой сведения о реализации инфраструктуры, используются для поддержки среды выполнения C и не должны вызываться напрямую из кода. В среде выполнения C используется *таблица функций onexit*, которая отражает последовательность функций, регистрируемых при вызовах `atexit`, `at_quick_exit` и `_onexit`. Таблица функций onexit содержит непрозрачные данные реализации среды выполнения C. Порядок и значения входящих в нее элементов данных могут изменяться. Внешний код проверять их не должен.

Функция `_initialize_onexit_table` возвращает таблицу функций onexit к исходным значениям.  Эту функцию необходимо вызывать до того, как таблица функций onexit будет передана в `_register_onexit_function` или `_execute_onexit_table`.

Функция `_register_onexit_function` добавляет функцию в конец таблицы функций onexit.

Функция `_execute_onexit_table` выполняет все функции из таблицы функций onexit, очищает таблицу и возвращается. После вызова `_execute_onexit_table` таблица переходит в недопустимое состояние; чтобы снова ее использовать, необходимо выполнить повторную инициализацию, вызвав `_initialize_onexit_table`.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h>|

Функции `_initialize_onexit_table`, `_register_onexit_function` и `_execute_onexit_table` относятся только к системам Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)