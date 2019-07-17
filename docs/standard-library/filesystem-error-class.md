---
title: Класс filesystem_error
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: c3dbfc080f0a1494950016f42189d932be05b0f1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240734"
---
# <a name="filesystemerror-class"></a>Класс filesystem_error

Базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.

## <a name="syntax"></a>Синтаксис

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Примечания

Этот класс служит базовым классом для всех исключений, уведомляющих об ошибке в функциях \<filesystem>. Он хранит объект типа `string`, который называется `mymesg` здесь в целях надстройках. Он также хранит два объекта типа `path`, который называется `mypval1` и `mypval2`.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[filesystem_error](#filesystem_error)|Создает `filesystem_error` сообщения.|

### <a name="functions"></a>Функции

|||
|-|-|
|[path1](#path1)|Возвращает `mypval1`.|
|[path2](#path2)|Возвращает `mypval2`.|
|[что](#what)|Возвращает указатель на `NTBS`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error

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

*what_arg*\
Указанное сообщение.

*EC*\
Указанный код ошибки.

*mypval1*\
Дополнительно указанным параметром сообщения.

*mypval2*\
Дополнительно оповещены с помощью указанного параметра.

## <a name="path1"></a> path1

Функция-член возвращает значение `mypval1`.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> path2

Функция-член возвращает значение `mypval2`.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> что

Функция-член возвращает указатель на `NTBS`, предпочтительно составлены из `runtime_error::what()`, `system_error::what()`, `mymesg`, `mypval1.native_string()`, и `mypval2.native_string()`.

```cpp
const char *what() const noexcept;
```
