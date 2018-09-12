---
title: Класс filesystem_error | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5756c01969dba0773e0327e1a34a0c7492b972a
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691527"
---
# <a name="filesystemerror-class"></a>Класс filesystem_error

Базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.

## <a name="syntax"></a>Синтаксис

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Примечания

Этот класс служит базовым классом для всех исключений, уведомляющих об ошибке в функциях \<filesystem>. Он хранит объект типа `string`, который называется `mymesg` здесь в целях надстройках. Он также хранит два объекта типа `path`, который называется `mypval1` и `mypval2`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[filesystem_error](#filesystem_error)|Создает `filesystem_error` сообщения.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[path1](#path1)|Возвращает `mypval1`.|
|[path2](#path2)|Возвращает `mypval2`.|
|[что](#what)|Возвращает указатель на `NTBS`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error::filesystem_error

Первый конструктор создает сообщение из *what_arg* и *ec*. Второй конструктор также создает сообщение из *pval1*, который хранит в `mypval1`. Третий конструктор также создает сообщение из *pval1*, сохраняет ее в `mypval1`и из *pval2*, который хранит в `mypval2`.

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

### <a name="parameters"></a>Параметры

*what_arg*<br/>
Указанное сообщение.

*EC*<br/>
Указанный код ошибки.

*mypval1*<br/>
Дополнительно указанным параметром сообщения.

*mypval2*<br/>
Дополнительно оповещены с помощью указанного параметра.

## <a name="path1"></a> filesystem_error::path1

Функция-член возвращает значение `mypval1`.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> filesystem_error::path2

Функция-член возвращает значение `mypval2`.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> filesystem_error::What

Функция-член возвращает указатель на `NTBS`, предпочтительно составлены из `runtime_error::what()`, `system_error::what()`, `mymesg`, `mypval1.native_string()`, и `mypval2.native_string()`.

```cpp
const char *what() const noexcept;
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Класс system_error](../standard-library/system-error-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
