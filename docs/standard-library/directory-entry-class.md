---
title: Класс directory_entry | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.workload:
- cplusplus
ms.openlocfilehash: 3c61d69c1ee5ad40191771dabd829514e3381e88
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691410"
---
# <a name="directoryentry-class"></a>Класс directory_entry

Описывает объект, возвращаемый `*X`, где *X* — [directory_iterator](../standard-library/directory-iterator-class.md) или [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class directory_entry;
```

## <a name="remarks"></a>Примечания

Класс сохраняет объект типа [path](../standard-library/path-class.md). Сохраненный `path` может быть экземпляром [класса path](../standard-library/path-class.md) или типом, производным от `path`. Он также сохраняет два значения [file_type](../standard-library/filesystem-enumerations.md#file_type); одно из них представляет то, что известно о состоянии сохраненного имени файла, а другое представляет то, что известно о состоянии символьной ссылки имени файла.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[directory_entry](#directory_entry)|Установленные по умолчанию конструкторы работают корректно. Четвертый конструктор инициализирует `mypath` для *pval*, `mystat` для *stat_arg*, и `mysymstat` для *symstat_arg*.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[assign](#assign)|Функция-член назначает *pval* для `mypath`, *stat* для `mystat`, и *symstat* для `mysymstat`.|
|[path](#path)|Функция-член возвращает значение `mypath`.|
|[replace_filename](#replace_filename)|Функция-член заменяет `mypath` с `mypath.parent_path()`  /  *pval*, `mystat` с *stat_arg*, и `mysymstat` с *symstat_arg*|
|[status](#status)|Обе функции-члены возвращают `mystat` возможно, во-первых изменена.|
|[symlink_status](#symlink_status)|Обе функции-члены возвращают `mysymstat` возможно, во-первых изменена.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор!=](#op_neq)|Заменяет элементы списка копией другого списка.|
|[оператор=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[оператор==](#op_eq)|Возвращает `mypath == right.mypath`.|
|[оператор<](#op_lt)|Возвращает `mypath < right.mypath`.|
|[оператор<=](#op_lteq)|Возвращает `!(right < *this)`.|
|[оператор>](#op_gt)|Возвращает `right < *this`.|
|[оператор>=](#op_gteq)|Возвращает `!(*this < right)`.|
|[оператор const path_type &](#path_type)|Возвращает `mypath`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<экспериментальная/filesystem&gt;

**Пространство имен:** std::experimental::filesystem

## <a name="assign"></a> назначить

Функция-член назначает *pval* для `mypath`, *stat_arg* для `mystat`, и *symstat_arg* для `mysymstat`.

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Путь имя сохраненного файла.  

*stat_arg*<br/>
Состояние имени сохраненного файла.  

*symstat_arg*<br/>
Состояние символьной ссылки имени сохраненного файла.  

## <a name="directory_entry"></a> directory_entry

Установленные по умолчанию конструкторы работают корректно. Четвертый конструктор инициализирует `mypath` для *pval*, `mystat` для *stat_arg*, и `mysymstat` для *symstat_arg*.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Путь имя сохраненного файла.  

*stat_arg*<br/>
Состояние имени сохраненного файла.  

*symstat_arg*<br/>
Состояние символьной ссылки имени сохраненного файла.  

## <a name="op_neq"></a> оператор! =

Функция-член возвращает значение `!(*this == right)`.

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) , с которым производится сравнение `directory_entry`.  

## <a name="op_as"></a> оператор =

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) копируется в `directory_entry`.  

## <a name="op_eq"></a> оператор ==

Функция-член возвращает значение `mypath == right.mypath`.

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) , с которым производится сравнение `directory_entry`.  

## <a name="op_lt"></a> Оператор&lt;

Функция-член возвращает значение `mypath < right.mypath`.

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) , с которым производится сравнение `directory_entry`.  

## <a name="op_lteq"></a> Оператор&lt;=

Функция-член возвращает значение `!(right < *this)`.

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) , с которым производится сравнение `directory_entry`.  

## <a name="op_gt"></a> Оператор&gt;

Функция-член возвращает значение `right < *this`.

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) , с которым производится сравнение `directory_entry`.  

## <a name="op_gteq"></a> Оператор&gt;=

Функция-член возвращает значение `!(*this < right)`.

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) , с которым производится сравнение `directory_entry`.  

## <a name="path_type"></a> оператор const path_type &

Оператор-член возвращает `mypath`.

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a> путь

Функция-член возвращает значение `mypath`.

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a> replace_filename

Функция-член заменяет `mypath` с `mypath.parent_path()`  /  *pval*, `mystat` с *stat_arg*, и `mysymstat` с *symstat_arg*

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Путь имя сохраненного файла.  

*stat_arg*<br/>
Состояние имени сохраненного файла.  

*symstat_arg*<br/>
Состояние символьной ссылки имени сохраненного файла.  

## <a name="status"></a> состояние

Обе функции-члены возвращают `mystat` возможно сначала изменить следующим образом:

1. Если `status_known(mystat)` не выполнять никаких действий.

1. В противном случае, если `!status_known(mysymstat) && !is_symlink(mysymstat)` затем `mystat = mysymstat`.

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Параметры

*EC*<br/>
Код состояния ошибки.  

## <a name="symlink_status"></a> symlink_status

Обе функции-члены возвращают `mysymstat` возможно сначала изменить следующим образом: Если `status_known(mysymstat)` не выполнять никаких действий. В противном случае — значение `mysymstat = symlink_status(mypval)`.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Параметры

*EC*<br/>
Код состояния ошибки.  

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<файловая система&gt;](../standard-library/filesystem.md)<br/>
