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

The [const](const-cpp.md) and [volatile](volatile-cpp.md) keywords change how pointers are treated. The **const** keyword specifies that the pointer cannot be modified after initialization; the pointer is protected from modification thereafter.

The **volatile** keyword specifies that the value associated with the name that follows can be modified by actions other than those in the user application. Therefore, the **volatile** keyword is useful for declaring objects in shared memory that can be accessed by multiple processes or global data areas used for communication with interrupt service routines.

When a name is declared as **volatile**, the compiler reloads the value from memory each time it is accessed by the program. Это значительно сокращает возможности оптимизации. Однако если состояние объекта может неожиданно изменяться, то это единственный способ гарантировать предсказуемую производительность программы.

To declare the object pointed to by the pointer as **const** or **volatile**, use a declaration of the form:

```cpp
const char *cpch;
volatile char *vpch;
```

To declare the value of the pointer — that is, the actual address stored in the pointer — as **const** or **volatile**, use a declaration of the form:

```cpp
char * const pchc;
char * volatile pchv;
```

The C++ language prevents assignments that would allow modification of an object or pointer declared as **const**. Такие присваивания могут удалить информацию, с которой был объявлен объект или указатель, и тем самым подменить смысл исходного объявления. Рассмотрим следующее объявление:

```cpp
const char cch = 'A';
char ch = 'B';
```

Given the preceding declarations of two objects (`cch`, of type **const char**, and `ch`, of type **char)** , the following declaration/initializations are valid:

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

В объявлении `pch2` задается указатель, при помощи которого может быть изменен постоянный объект, поэтому это объявление запрещено. The declaration of `pch3` specifies that the pointer is constant, not the object; the declaration is disallowed for the same reason the `pch2` declaration is disallowed.

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

Pointers declared as **volatile**, or as a mixture of **const** and **volatile**, obey the same rules.

Pointers to **const** objects are often used in function declarations as follows:

```cpp
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );
```

The preceding statement declares a function, [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), where two of the three arguments are of type pointer to **char**. Because the arguments are passed by reference and not by value, the function would be free to modify both `strDestination` and `strSource` if `strSource` were not declared as **const**. The declaration of `strSource` as **const** assures the caller that `strSource` cannot be changed by the called function.

> [!NOTE]
> Because there is a standard conversion from *typename* <strong>\*</strong> to **const** *typename* <strong>\*</strong>, it is legal to pass an argument of type `char *` to [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). However, the reverse is not true; no implicit conversion exists to remove the **const** attribute from an object or pointer.

A **const** pointer of a given type can be assigned to a pointer of the same type. However, a pointer that is not **const** cannot be assigned to a **const** pointer. В следующем коде показано одно верное и одно неверное присваивание.

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

## <a name="see-also"></a>См. также

[Pointers](pointers-cpp.md)
[Raw pointers](raw-pointers.md)