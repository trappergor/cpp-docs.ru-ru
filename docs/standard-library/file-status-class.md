---
title: Класс file_status
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.openlocfilehash: 81ce4ecc1673087db8e985f94e297798dd712a6e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160021"
---
# <a name="filestatus-class"></a>Класс file_status

Создает оболочку для [file_type](../standard-library/filesystem-enumerations.md#file_type) и [perms](../standard-library/filesystem-enumerations.md#perms).

## <a name="syntax"></a>Синтаксис

```cpp
class file_status;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[file_status](#file_status)|Создает оболочку для [file_type](../standard-library/filesystem-enumerations.md#file_type) и файл [perms](../standard-library/filesystem-enumerations.md#perms).|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[type](#type)|Возвращает или задает класс `file_type`.|
|[permissions](#permissions)|Возвращает или задает разрешения для файла.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental:: FileSystem, std::experimental:: FileSystem

## <a name="file_status"></a> file_status::file_status

Создает оболочку для [file_type](../standard-library/filesystem-enumerations.md#file_type) и файл [perms](../standard-library/filesystem-enumerations.md#perms).

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>Параметры

*ftype*<br/>
Указанный `file_type`, по умолчанию используется `file_type::none`.

*Маска*<br/>
Указанный файл `perms`, по умолчанию используется `perms::unknown`.

*file_status*<br/>
Сохраненный объект.

## <a name="op_as"></a> file_status::operator=

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>Параметры

*file_status*<br/>
[File_status](../standard-library/file-status-class.md) копируется в `file_status`.

## <a name="type"></a> Тип

Возвращает или задает класс `file_type`.

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>Параметры

*ftype*<br/>
Задается следующим образом: `file_type`.

## <a name="permissions"></a> Разрешения

Возвращает или задает разрешения для файла.

Используйте метод задания, чтобы создать файл `readonly` или удалите `readonly` атрибута.

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>Параметры

*Маска*<br/>
Задается следующим образом: `perms`.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Класс path](../standard-library/path-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
