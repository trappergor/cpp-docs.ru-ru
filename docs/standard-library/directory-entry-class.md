---
title: Класс directory_entry | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
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
ms.openlocfilehash: ba3dc5588cb035cb754ba43a6eeccb37b7ec0b79
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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

## <a name="assign"></a>assign

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Функция-член назначает pval объекту mypath, stat объекту mystat и symstat объекту mysymstat.

## <a name="directoryentry"></a>directory_entry

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Установленные по умолчанию конструкторы работают корректно. Четвертый конструктор инициализирует mypath значением pval, mystat значением stat_arg и mysymstat значением symstat_arg.

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

Функция-член возвращает значение !(*this == right).

## <a name="operator"></a>operator=

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

Операторы-члены присваивания по умолчанию работают корректно.

## <a name="operator"></a>operator==

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

Функция-член возвращает значение mypath == right.mypath.

## <a name="operatorlt"></a>Оператор&lt;

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

Функция-член возвращает mypath &lt; right.mypath.

## <a name="operatorlt"></a>оператор&lt;=

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

Функция-член возвращает значение !(right \< *this).

## <a name="operatorgt"></a>Оператор&gt;

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

Функция-член возвращает значение right \< *this.

## <a name="operatorgt"></a>оператор&gt;=

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

Функция-член возвращает! (* это \< справа).

## <a name="operator-const-pathtype"></a>operator const path_type&

```cpp
operator const std::experimental::filesystem::path&() const;
```

Оператор-член возвращает mypath.

## <a name="path"></a>путем

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

Функция-член возвращает значение mypath.

## <a name="replacefilename"></a>replace_filename

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Функция-член заменяет mypath значением mypath.parent_path() / pval, mystat значением stat_arg и mysymstat значением symstat_arg.

## <a name="status"></a>status

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

Обе функции-члены возвращают mystat, возможно, сначала изменив его следующим образом:

1. если status_known(mystat), не выполнять никаких действий.

1. В противном случае, если !status_known(mysymstat) && !is_symlink(mysymstat), то mystat = mysymstat.

## <a name="symlinkstatus"></a>symlink_status

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

Обе функции-члены возвращают mysymstat, возможно, сначала изменив его следующим образом: если status_known(mysymstat), не выполнять никаких действий. В противном случае mysymstat = symlink_status(mypval).

## <a name="requirements"></a>Требования

**Заголовок:** \<экспериментальный/файловой системы&gt;

**Пространство имен:** std::experimental::filesystem

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Файловая система&gt;](../standard-library/filesystem.md)<br/>
