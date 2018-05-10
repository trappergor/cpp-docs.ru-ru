---
title: Класс vector&lt;bool&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- vector<bool>
- vector/std::vector::const_pointer
- vector/std::vector::const_reference
- vector/std::vector::pointer
- vector/std::vector::flip
- vector/std::vector::swap
dev_langs:
- C++
helpviewer_keywords:
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], pointer
- std::vector [C++], flip
- std::vector [C++], swap
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab7f4e185f19b07ddcec47b8f167e7040a5bef28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="vectorltboolgt-class"></a>Класс vector&lt;bool&gt;

Класс `vector<bool>` является частичной специализацией объекта [vector](../standard-library/vector-class.md) для элементов типа `bool`. Он имеет распределитель базового типа, который используется специализацией, обеспечивающей оптимизацию пространства путем сохранения одного значения `bool` на бит.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>Примечания

Поведение данной специализации шаблона класса аналогично поведению класса vector, за исключением различий, указанных в данной статье.

Операции, которые работают с типом `bool`, соответствуют значениям в хранилище контейнера. Параметр `allocator_traits::construct` не используется для создания данных значений.

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_pointer](#const_pointer)|Typedef для итератора `const_iterator`, который может применяться как указатель константы на логический элемент `vector<bool>`.|
|[const_reference](#const_reference)|Typedef для `bool`. После инициализации данный объект не проверяет наличие обновлений исходного значения.|
|[pointer](#pointer)|Typedef для итератора `iterator`, который может применяться как указатель на логический элемент `vector<bool>`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[flip](#flip)|Обращает все биты в `vector<bool>`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `vector<bool>`.|
|[operator&#91;&#93;](#op_at)|Возвращает смоделированной ссылку на элемент `vector<bool>` в указанную позицию.|
|`at`|Функция аналогична неспециализированной функции [vector](../standard-library/vector-class.md)::at за исключением того, что в ней используется прокси-класс [vector\<bool>::reference](#reference_class). См. также [operator[]](#op_at).|
|`front`|Функция аналогична неспециализированной функции [vector](../standard-library/vector-class.md)::front за исключением того, что в ней используется прокси-класс [vector\<bool>::reference](#reference_class). См. также [operator[]](#op_at).|
|`back`|Функция аналогична неспециализированной функции [vector](../standard-library/vector-class.md)::back за исключением того, что в ней используется прокси-класс [vector\<bool>::reference](#reference_class). См. также [operator[]](#op_at).|

### <a name="proxy-class"></a>Прокси-класс

|||
|-|-|
|Класс [vector\<bool>](#reference_class)|Класс, действующий как прокси для моделирования поведения `bool&`, объекты которого могут предоставлять ссылки на элементы (одиночные биты) в пределах объекта `vector<bool>`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<vector>

**Пространство имен:** std

## <a name="const_pointer"></a>  vector\<bool>::const_pointer

Тип, описывающий объект, который можно использовать в качестве константного указателя на логический элемент последовательности, содержащейся объектом `vector<bool>`.

```cpp
typedef const_iterator const_pointer;
```

## <a name="const_reference"></a>  vector\<bool>::const_reference

Тип, описывающий объект, который можно использовать в качестве константной ссылки на логический элемент последовательности, содержащейся объектом `vector<bool>`.

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения и примеры кода см. в разделе [vector&lt;bool&gt;::reference::operator=](#reference_operator_eq).

## <a name="flip"></a>  vector\<bool>::flip

Реверсирует все биты в `vector<bool>`.

```cpp
void flip();
```

### <a name="example"></a>Пример

```cpp
// vector_bool_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha; // format output for subsequent code

    vector<bool> vb = { true, false, false, true, true };
    cout << "The vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vb.flip();

    cout << "The flipped vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}

```

## <a name="op_at"></a>  vector\<bool>::operator[]

Возвращает смоделированной ссылку на элемент `vector<bool>` в указанную позицию.

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|-|-|
|`Pos`|Позиция элемента `vector<bool>`.|

### <a name="return-value"></a>Возвращаемое значение

Объект [vector\<bool>::reference](#reference_class) или [vector\<bool>::const_reference](#const_reference), который содержит значение индексированного элемента.

Если заданная позиция больше или равна размеру контейнера, результат не определен.

### <a name="remarks"></a>Примечания

При компиляции с набором `_ITERATOR_DEBUG_LEVEL` возникает ошибка во время выполнения, если предпринимается попытка доступа к элементу за пределами вектора.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

Этот пример кода демонстрирует правильное использование элемента `vector<bool>::operator[]` и две стандартных ошибки кодирования с комментариями. Подобные ошибки вызывают ошибки во время использования кода, поскольку адрес объекта `vector<bool>::reference`, возвращающего `vector<bool>::operator[]`, не может быть извлечен.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;
    vector<bool> vb;

    vb.push_back(true);
    vb.push_back(false);

    //    bool* pb = &vb[1]; // conversion error - do not use
    //    bool& refb = vb[1];   // conversion error - do not use
    bool hold = vb[1];
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;

    // Note this doesn't modify hold.
    vb[1] = true;
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;
}
```

## <a name="pointer"></a>  vector\<bool>::pointer

Тип, описывающий объект, который можно использовать в качестве указателя на логический элемент последовательности, содержащейся объектом `vector<bool>`.

```cpp
typedef iterator pointer;
```

## <a name="reference_class"></a>  Класс vector\<bool>::reference

Класс `vector<bool>::reference` — это прокси-класс, предоставленный классом [vector\<bool> ](../standard-library/vector-bool-class.md) для моделирования `bool&`.

### <a name="remarks"></a>Примечания

Необходима смоделированная ссылка, поскольку C++ изначально не допускает прямых ссылок на биты. `vector<bool>` использует только один бит на элемент, ссылку на который можно создать с помощью данного класса прокси. Однако моделирование ссылки является незавершенным, поскольку определенные назначения не являются допустимыми. Например, следующий пример использования объекта [vector\<bool>::operator[]](#op_at) является неправильным, так как невозможно получить адрес объекта `vector<bool>::reference`:

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

###  <a name="reference_flip"></a>  vector\<bool>::reference::flip

Инвертирует логическое значение для элемента вектора [vector\<bool>](../standard-library/vector-bool-class.md) по ссылке.

```cpp
void flip();
```

#### <a name="example"></a>Пример

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

###  <a name="reference_operator_bool"></a>  vector\<bool>::reference::operator bool

Обеспечивает неявное преобразование из `vector<bool>::reference` в `bool`.

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Логическое значение элемента объекта vector\<bool>.

#### <a name="remarks"></a>Примечания

Объект `vector<bool>` невозможно изменить при помощи данного оператора.

###  <a name="reference_operator_eq"></a>  vector\<bool>::reference::operator=

Присваивает биту логическое значение или значение, которое содержит элемент со ссылкой.

```cpp
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```

### <a name="parameters"></a>Параметры

`Right` Ссылка на элемент, значение которого должен быть присвоено биту.

`Val` Логическое значение, присваиваемое бит.

#### <a name="example"></a>Пример

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}
```

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="swap"></a>  vector\<bool>::swap

Статическая функция-член, которая меняет местами два элемента логических векторов (`vector<bool>`) с помощью прокси-класса [vector\<bool>::reference](#reference_class).

```cpp
static void swap(
    reference Left,
    reference Right);
```

### <a name="parameters"></a>Параметры

`Left` Элемент для обмена на `Right` элемент.

`Right` Элемент для обмена на `Left` элемент.

### <a name="remarks"></a>Примечания

Данная перегрузка поддерживает специальные прокси-требования `vector<bool>`. [vector::swap](../standard-library/vector-class.md) имеет те же функции, что и одноаргументная перегрузка `vector<bool>::swap()`.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
