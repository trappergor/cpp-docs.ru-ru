---
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 8164f47190267627bdaf7c7ee2f03f22f65c8f50
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161065"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Блок, относящийся только к системам Microsoft**

**__Declspec** Расширенный атрибут, который можно использовать в объявлении функций.

## <a name="syntax"></a>Синтаксис

> __declspec *возвращаемого типа* (throw) [*соглашение о вызовах*] *функция-имя* ([*Argument-List*])

## <a name="remarks"></a>Remarks

Рекомендуется, чтобы в новом коде использовался оператор [except](noexcept-cpp.md) , а не `__declspec(nothrow)`.

Этот атрибут сообщает компилятору, что и объявленная функция, и функции, которые она вызывает, никогда не создают исключений. Однако директива не применяется. Иными словами, он никогда не вызывает [std:: Terminate](../standard-library/exception-functions.md#terminate) , в отличие от `noexcept`или в режиме **std: C++ 17** (Visual Studio 2017 версии 15,5 и более поздних), `throw()`.

Поскольку по умолчанию теперь используется модель синхронной обработки исключений, то компилятор может исключить механизм, позволяющий отслеживать время существования удаляемых объектов в такой функции, и значительно уменьшить объем кода. При наличии следующей директивы препроцессора три приведенные ниже объявления функций эквивалентны в режиме **/std: c++ 14** :

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

В **/std: режим c++ 17** `throw()` не эквивалентен другим, использующим `__declspec(nothrow)`, поскольку он вызывает вызов `std::terminate`, если из функции порождается исключение.

В объявлении `void __stdcall f3() throw();` используется синтаксис, определенный C++ стандартом. В C++ 17 ключевое слово `throw()` устарело.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
