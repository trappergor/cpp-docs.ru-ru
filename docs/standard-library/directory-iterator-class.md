---
title: Класс directory_iterator
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: 8c6dcce3de32c7e25d2489cb508454dff500a1a6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454416"
---
# <a name="directoryiterator-class"></a>Класс directory_iterator

Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге. Для итератора `X`результатом выражения `*X` является объект класса `directory_entry` , который заключает в оболочку имя файла и все известные сведения о его состоянии.

Класс `path`сохраняет объект типа, вызываемый `mydir` здесь в целях демонстрации, который представляет имя каталога для упорядочения, и объект типа `directory_entry` , который вызывается `myentry` здесь, который представляет текущий имя файла в последовательности каталогов. Созданный по умолчанию объект типа `directory_entry` имеет пустой `mydir` путь и представляет итератор конца последовательности.

Например, при наличии каталога `abc` с записями `def` и `ghi`, код:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

будет вызывать `visit` с аргументами `path("abc/def")` и `path("abc/ghi")`.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[directory_iterator](#directory_iterator)|Конструирует входной итератор, подающий последовательность по именам файлов в каталоге.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[производим](#increment)|Пытается перейти к следующему имени файла в каталоге.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](#op_neq)|Возвращает `!(*this == right)`.|
|[оператор=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[operator==](#op_eq)|Возвращает **значение true** , только `*this` если оба и *правные* стороны являются итераторами конца последовательности или оба не являются итераторами конца последовательности.|
|[оператор*](#op_star)|Возвращает `myentry`.|
|[оператор>](#op_cast)|Возвращает `&**this`.|
|[оператор++](#op_increment)|Вызывает `increment()`, затем возвращает `*this`или создает копию объекта, вызывает `increment()`, а затем возвращает копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<experimental/filesystem>

**Пространство имен:** std::experimental::filesystem

## <a name="directory_iterator"></a>directory_iterator::d irectory_iterator

Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы хранят *Pval* в `mydir`, а затем пытаются открыть и прочитать `mydir` в виде каталога. В случае успеха они сохраняют первое имя файла в каталоге в `myentry`; в противном случае они создают итератор конца последовательности.

Установленные по умолчанию конструкторы работают корректно.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*Pval*\
Путь к сохраненному имени файла.

*контроллер*\
Код ошибки состояния.

*directory_iterator*\
Сохраненный объект.

## <a name="increment"></a>directory_iterator:: Increment

Функция пытается перейти к следующему файлу в каталоге. В случае успеха файл сохраняется в `myentry`; в противном случае — итератор конца последовательности.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a>directory_iterator:: operator! =

Оператор-член возвращает `!(*this == right)`.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*Правильно*\
[Directory_iterator](../standard-library/directory-iterator-class.md) сравнивается `directory_iterator`с.

## <a name="op_as"></a>directory_iterator:: operator =

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*Правильно*\
[Directory_iterator](../standard-library/directory-iterator-class.md) копируется `directory_iterator`в.

## <a name="op_eq"></a>directory_iterator:: operator = =

Оператор-член возвращает **значение true** , только `*this` если оба и *право* являются итераторами конца последовательности или оба являются итераторами конца последовательности.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*Правильно*\
[Directory_iterator](../standard-library/directory-iterator-class.md) сравнивается `directory_iterator`с.

## <a name="op_star"></a>directory_iterator:: operator *

Оператор-член возвращает `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> directory_iterator::operator->

Функция-член возвращает значение `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>directory_iterator:: operator + +

Первая функция – член вызывает `increment()`, а затем `*this`возвращает. Вторая функция-член создает копию объекта, вызывает `increment()`, а затем возвращает копию.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Параметры

*int*\
Число приращений.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)
