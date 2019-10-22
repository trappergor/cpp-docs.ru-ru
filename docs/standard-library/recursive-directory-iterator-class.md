---
title: Класс recursive_directory_iterator
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: a5200c030986ebbcfccb1eba2963e8317c879eb6
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686804"
---
# <a name="recursive_directory_iterator-class"></a>Класс recursive_directory_iterator

Описывает итератор ввода, который помещает через имена файлов в каталоге, возможно, по убыванию в подкаталогах рекурсивно. Для `X` итератора выражение `*X` вычисляет объект класса `directory_entry`, который упаковывает имя файла и все известные сведения о его состоянии.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Заметки

В шаблоне класса хранятся:

1. Объект типа `stack<pair<directory_iterator, path>>`, который вызывается `mystack` здесь для целей демонстрации, представляющих вложенность каталогов для упорядочения.

1. Объект типа `directory_entry` под именем `myentry`, который представляет текущее имя файла в последовательности каталогов.

1. Объект типа **bool**, именуемый `no_push` здесь, который записывает, отключена ли рекурсивная спуск в подкаталогах

1. Объект типа `directory_options`, именуемый `myoptions` здесь, в котором записываются параметры, созданные при создании

Созданный по умолчанию объект типа `recursive_directory_entry` имеет итератор конца последовательности в `mystack.top().first` и представляет итератор конца последовательности. Например, при наличии каталога `abc` с записями `def` (каталог), `def/ghi` и `jkl`, код:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

вызовет Visit с аргументами `path("abc/def/ghi")` и `path("abc/jkl")`. Можно определить последовательность через поддерево каталога двумя способами.

1. Каталог символьную ссылку будет проверяться только при создании `recursive_directory_iterator` с `directory_options`ным аргументом, значение которого равно `directory_options::follow_directory_symlink`.

1. При вызове `disable_recursion_pending` следующий каталог, обнаруженный во время инкремента, не будет рекурсивно проверен.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Создает документ `recursive_directory_iterator`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[Длина](#depth)|Возвращает `mystack.size() - 1`, поэтому `pval` имеет нулевую глубину.|
|[disable_recursion_pending](#disable_recursion_pending)|Сохраняет **значение true** в `no_push`.|
|[производим](#increment)|Переходит к следующему имени файла в последовательности.|
|[options](#options)|Возвращает `myoptions`.|
|[pop](#pop)|Возвращает следующий объект.|
|[recursion_pending](#recursion_pending)|Возвращает `!no_push`.|

### <a name="operators"></a>Операторы

|оператора|Описание|
|-|-|
|[оператор!= ](#op_neq)|Возвращает `!(*this == right)`.|
|[оператор=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[оператор==](#op_eq)|Возвращает **значение true** , только если оба `*this` и *right* являются итераторами конца последовательности или оба являются итераторами конца последовательности.|
|[operator*](#op_multiply)|Возвращает `myentry`.|
|[оператор>](#op_cast)|Возвращает `&**this`.|
|[оператор++](#op_increment)|Увеличивает `recursive_directory_iterator`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::tr2::sys

## <a name="depth"></a>recursive_directory_iterator::d ЕПС

Возвращает `mystack.size() - 1`, поэтому `pval` имеет нулевую глубину.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a>recursive_directory_iterator::d isable_recursion_pending

Сохраняет **значение true** в `no_push`.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a>recursive_directory_iterator:: Increment

Переходит к следующему имени файла в последовательности.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Параметры

*ec* \
Указанный код ошибки.

### <a name="remarks"></a>Заметки

Функция пытается перейти к имени следующего файла во вложенной последовательности. В случае успеха имя файла сохраняется в `myentry`; в противном случае он создает итератор конца последовательности.

## <a name="op_neq"></a>recursive_directory_iterator:: operator! =

Возвращает `!(*this == right)`.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*справа* \
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для сравнения.

## <a name="op_as"></a>recursive_directory_iterator:: operator =

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*recursive_directory_iterator* \
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) копируется в `recursive_directory_iterator`.

## <a name="op_eq"></a>recursive_directory_iterator:: operator = =

Возвращает **значение true** , только если оба `*this` и *right* являются итераторами конца последовательности или оба являются итераторами конца последовательности.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*справа* \
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для сравнения.

## <a name="op_multiply"></a>recursive_directory_iterator:: operator *

Возвращает `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>recursive_directory_iterator:: operator — >

Возвращает `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>recursive_directory_iterator:: operator + +

Увеличивает `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Параметры

\ *int*
Указанное приращение.

### <a name="remarks"></a>Заметки

Первая функция члена вызывает `increment()`, а затем возвращает `*this`. Вторая функция-член создает копию объекта, вызывает `increment()`, а затем возвращает копию.

## <a name="options"></a>recursive_directory_iterator:: параметры

Возвращает `myoptions`.

```cpp
directory_options options() const;
```

## <a name="pop"></a>recursive_directory_iterator::p Op

Возвращает следующий объект.

```cpp
void pop();
```

### <a name="remarks"></a>Заметки

Если `depth() == 0` объект станет итератором конца последовательности. В противном случае функция-член завершает проверку текущего (самого глубокого) каталога и возобновляет ее на следующем нижнем уровне глубины.

## <a name="recursion_pending"></a>recursive_directory_iterator::recursion_pending

Возвращает `!no_push`.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a>recursive_directory_iterator::recursive_directory_iterator

Создает документ `recursive_directory_iterator`.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*pval* \
Заданный путь.

*error_code* \
Указанный код ошибки.

на\
Указанные параметры каталога.

*recursive_directory_iterator* \
`recursive_directory_iterator`, копией которого будет создаваемый `recursive_directory_iterator`.

### <a name="remarks"></a>Заметки

Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы сохраняют **значение false** в `no_push` и `directory_options::none` в `myoptions`, а затем пытаются открыть и прочитать *Pval* как каталог. В случае успеха они инициализируют `mystack` и `myentry`, чтобы назначить первое имя файла, не являющегося каталогом, во вложенной последовательности. в противном случае они создают итератор конца последовательности.

Четвертый и пятый конструкторы ведут себя так же, как во втором и третьем, за исключением того, что они *сначала хранят в* `myoptions`. Установленные по умолчанию конструкторы работают корректно.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)
