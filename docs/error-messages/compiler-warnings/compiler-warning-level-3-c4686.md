---
title: Предупреждение компилятора (уровень 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 5e23e6aa69fe8a59e3dfd22af7e33780c223cdd3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584526"
---
# <a name="compiler-warning-level-3-c4686"></a>Предупреждение компилятора (уровень 3) C4686

> "*определяемого пользователем типа*": возможное изменение поведения, изменение возвращаемого значения UDT соглашение о вызовах

## <a name="remarks"></a>Примечания

Специализация шаблона класса не был задан до ее использования в тип возвращаемого значения. Все, что создает экземпляр класса разрешит C4686; объявление экземпляра или доступ к члену (C\<int >:: ничего) также являются параметры.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

Вместо этого попробуйте сделайте следующее:

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