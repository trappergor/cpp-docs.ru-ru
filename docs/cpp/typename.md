---
title: Ключевое слово typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 789bb879922bbd96a04085159205d02fb7f495c8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160688"
---
# <a name="typename"></a>Ключевое слово typename

В определениях шаблонов предоставляет компилятору указание о том, что неизвестный идентификатор является типом. В списках параметров шаблона используется для указания параметра типа.

## <a name="syntax"></a>Синтаксис

```
typename identifier;
```

## <a name="remarks"></a>Remarks

Это ключевое слово следует использовать, если имя в определении шаблона является полным именем, которое зависит от аргумента шаблона. Это необязательно, если полное имя не зависит от. Дополнительные сведения см. в разделе [шаблоны и разрешение имен](../cpp/templates-and-name-resolution.md).

**имя TypeName** может использоваться любым типом в любом месте в объявлении или определении шаблона. В списке базовых классов оно не допускается, если не применяется в качестве аргумента шаблона для базового класса шаблона.

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

Ключевое слово **TypeName** можно также использовать вместо **класса** в списках параметров шаблона. Например, следующие операторы семантически эквивалентны:

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>Пример

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>См. также раздел

[Шаблоны](../cpp/templates-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
