---
title: Предупреждение компилятора (уровень 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: a8eae1ddeb875d267b82c67e989cb41e8c9b2afb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185455"
---
# <a name="compiler-warning-level-3-c4686"></a>Предупреждение компилятора (уровень 3) C4686

> "*определяемый пользователем тип*": возможное изменение в поведении, изменение соглашения о вызовах для возврата определяемого пользователем типа

## <a name="remarks"></a>Remarks

Специализация шаблона класса не определена до ее использования в возвращаемом типе. Все, что создает экземпляр класса, будет разрешать C4686; объявление экземпляра или доступ к элементу (C\<int >:: любые) также являются параметрами.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

Вместо этого попробуйте выполнить следующие действия:

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```
