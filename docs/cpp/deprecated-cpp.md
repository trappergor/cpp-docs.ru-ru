---
title: deprecated (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: e4689d3cb1a1757e2ac3bf4ca9eef7670ad5c655
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189485"
---
# <a name="deprecated-c"></a>deprecated (C++)

В этом разделе рассматриваются устаревшие объявления declspec, относящиеся к Microsoft. Дополнительные сведения об атрибуте `[[deprecated]]` c++ 14 и рекомендации по использованию этого атрибута и declspec или директивы pragma Майкрософт см. в разделе [ C++ стандартные атрибуты](attributes.md).

В приведенных ниже исключениях **нерекомендуемое** объявление предоставляет те же функциональные возможности, что и [нерекомендуемая](../preprocessor/deprecated-c-cpp.md) директива pragma:

- **Нерекомендуемое** объявление позволяет указывать определенные формы перегрузок функций как устаревшие, в то время как форма pragma применяется ко всем перегруженным формам имени функции.

- **Нерекомендуемое** объявление позволяет указать сообщение, которое будет отображаться во время компиляции. Текст сообщения может быть взят из макроса.

- Макросы могут быть помечены как нерекомендуемые с помощью **нерекомендуемой** директивы pragma.

Если компилятор обнаруживает использование устаревшего идентификатора или стандартного атрибута [`[[deprecated]]`](attributes.md) , выдается предупреждение [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) .

## <a name="example"></a>Пример

В следующем примере показано, как отметить функции как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемая функция.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

## <a name="example"></a>Пример

В следующем примере показано, как отметить классы как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемый класс.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
