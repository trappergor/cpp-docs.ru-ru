---
title: Указатели с ключевыми словами const и volatile
ms.date: 11/19/2019
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
ms.openlocfilehash: c0aafde9070275abcb270710e2d4a7a8d9806267
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246633"
---
# <a name="const-and-volatile-pointers"></a>Указатели с ключевыми словами const и volatile

Ключевые слова [const](const-cpp.md) и [volatile](volatile-cpp.md) изменяют, как обрабатываются указатели. Ключевое слово **const** указывает, что указатель не может быть изменен после инициализации; После этого указатель защищен от изменения.

Ключевое слово **volatile** указывает, что значение, связанное с указанным ниже именем, может быть изменено действиями, отличными от тех, которые используются в пользовательском приложении. Таким образом, ключевое слово **volatile** полезно для объявления объектов в общей памяти, к которым можно получить доступ с помощью нескольких процессов или глобальных областей данных, используемых для связи с процедурами службы прерываний.

Если имя объявлено как **volatile**, компилятор повторно загружает значение из памяти при каждом доступе программы. Это значительно сокращает возможности оптимизации. Однако если состояние объекта может неожиданно изменяться, то это единственный способ гарантировать предсказуемую производительность программы.

Чтобы объявить объект, на который указывает указатель, как **const** или **volatile**, используйте объявление формы:

```cpp
const char *cpch;
volatile char *vpch;
```

Чтобы объявить значение указателя, то есть фактический адрес, хранящийся в указателе — как **const** или **volatile**, используйте объявление формы:

```cpp
char * const pchc;
char * volatile pchv;
```

Язык не позволяет назначениям допускать изменение объекта или указателя, объявленного как **const.** C++ Такие присваивания могут удалить информацию, с которой был объявлен объект или указатель, и тем самым подменить смысл исходного объявления. Рассмотрим следующее объявление:

```cpp
const char cch = 'A';
char ch = 'B';
```

Учитывая приведенные выше объявления двух объектов (`cch`, типа **const char**и `ch`типа **char)** , допустимы следующие объявления и инициализации:

```cpp
const char *pch1 = &cch;
const char *const pch4 = &cch;
const char *pch5 = &ch;
char *pch6 = &ch;
char *const pch7 = &ch;
const char *const pch8 = &ch;
```

Следующие объявления и инициализации вызывают ошибки.

```cpp
char *pch2 = &cch;   // Error
char *const pch3 = &cch;   // Error
```

В объявлении `pch2` задается указатель, при помощи которого может быть изменен постоянный объект, поэтому это объявление запрещено. Объявление `pch3` указывает, что указатель является константой, а не объектом; объявление не разрешено по той же причине, что объявление `pch2` запрещено.

В следующих восьми примерах демонстрируется присваивание через указатель и изменение значения указателя для приведенных выше объявлений. Здесь мы предполагаем, что инициализация указателей `pch1`–`pch8` была выполнена без ошибок.

```cpp
*pch1 = 'A';  // Error: object declared const
pch1 = &ch;   // OK: pointer not declared const
*pch2 = 'A';  // OK: normal pointer
pch2 = &ch;   // OK: normal pointer
*pch3 = 'A';  // OK: object not declared const
pch3 = &ch;   // Error: pointer declared const
*pch4 = 'A';  // Error: object declared const
pch4 = &ch;   // Error: pointer declared const
```

Указатели, объявленные как **volatile**, или как сочетание **const** и **volatile**, подчиняются тем же правилам.

Указатели на **константные** объекты часто используются в объявлениях функций следующим образом:

```cpp
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );
```

В предыдущем операторе объявляется функция, [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), где два из трех аргументов имеют тип указателя на **char**. Поскольку аргументы передаются по ссылке, а не по значению, функция может изменить как `strDestination`, так и `strSource`, если `strSource` не были объявлены как **const**. Объявление `strSource` как **const** гарантирует, что вызывающий объект, который `strSource` не может быть изменен вызываемой функцией.

> [!NOTE]
> Так как существует стандартное преобразование из *typename* <strong>\*</strong> в **константу** *typename* <strong>\*</strong>, допустимо передавать аргумент типа `char *` в [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Однако обратная не имеет значения true; не существует неявного преобразования для удаления атрибута **const** из объекта или указателя.

Указатель на **константу** данного типа может быть назначен указателю того же типа. Однако указатель, который не является **константой** , не может быть назначен **константному** указателю. В следующем коде показано одно верное и одно неверное присваивание.

```cpp
// const_pointer.cpp
int *const cpObject = 0;
int *pObject;

int main() {
pObject = cpObject;
cpObject = pObject;   // C3892
}
```

В следующем примере показано, как объявить объект как const, когда имеется указатель на указатель на объект.

```cpp
// const_pointer2.cpp
struct X {
   X(int i) : m_i(i) { }
   int m_i;
};

int main() {
   // correct
   const X cx(10);
   const X * pcx = &cx;
   const X ** ppcx = &pcx;

   // also correct
   X const cx2(20);
   X const * pcx2 = &cx2;
   X const ** ppcx2 = &pcx2;
}
```

## <a name="see-also"></a>См. также:

[Указатели](pointers-cpp.md)
[необработанные указатели](raw-pointers.md)