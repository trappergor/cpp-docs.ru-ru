---
title: deprecated (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 262b23e6e4813a5e22bc3f4e7c9a18efb9988a7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389298"
---
# <a name="deprecated-cc"></a>deprecated (C/C++)

**Устаревшим** директива #pragma позволяет указать, что функции, тип или любой другой идентификатор может не поддерживаться в будущем выпуске или больше не используется.

> [!NOTE]
> Сведения о C ++ 14 `[[deprecated]]` атрибута и рекомендации по использованию, атрибут vs Microsoft declspec или директиву pragma, см. в разделе [стандартные атрибуты C++](../cpp/attributes.md) атрибута.

## <a name="syntax"></a>Синтаксис

```
#pragma deprecated( identifier1 [,identifier2, ...] )
```

## <a name="remarks"></a>Примечания

Когда компилятор встречает идентификатор, указанный **устаревшим** pragma, он выдает предупреждение компилятора [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).

Имена макросов можно объявить нерекомендуемыми. Поместите имя макроса в кавычки; в противном случае произойдет расширение макроса.

Так как **устаревшим** pragma работает на всех сопоставления идентификаторов, а также учитывает подписи, его не наилучший вариант устаревания конкретных версий перегруженных функций. Любое сопоставления имя функции, которое вносится в область действия вызывает предупреждение.

Мы рекомендуем использовать C ++ 14 `[[deprecated]]` атрибут, по возможности вместо **устаревшим** директивы pragma. Присущий Майкрософт [__declspec(deprecated)](../cpp/deprecated-cpp.md) модификатора объявления также является лучшим выбором во многих случаях, чем **устаревшим** директивы pragma. `[[deprecated]]` Атрибут и `__declspec(deprecated)` модификатор позволяют определить нерекомендуемое состояние для отдельных форм перегруженных функций. Предупреждение диагностики отображается только для ссылок на определенные перегруженной функции атрибут или модификатор применяется к.

## <a name="example"></a>Пример

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

В следующем примере показано, как объявить класс устаревшим.

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)