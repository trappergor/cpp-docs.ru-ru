---
title: Устарело (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- deprecated_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3efc793e5030fa86c3bd1214ef4b8b408361a4ef
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409089"
---
# <a name="deprecated-c"></a>deprecated (C++)
Этот раздел посвящен присущий Майкрософт рекомендуется использовать объявления declspec. Сведения о C ++ 14 `[[deprecated]]` атрибута и рекомендации по использованию этого атрибута и характерные для Майкрософт declspec или директиву pragma, см. в разделе [стандартные атрибуты C++](attributes.md).

 За исключением указанных ниже **устаревшим** объявление предлагает ту же функциональность, что [устаревшим](../preprocessor/deprecated-c-cpp.md) директивы pragma:  
  
-   **Устаревшим** объявление позволяет указать определенные формы перегрузок функций как нерекомендуемые, тогда как форма директивы pragma применяется ко всем перегруженным формам имени функции.  
  
-   **Устаревшим** объявление позволяет указать сообщение, которое будет отображаться во время компиляции. Текст сообщения может быть взят из макроса.  
  
-   Макросы могут отмечаться только как нерекомендуемые с **устаревшим** директивы pragma.  
  
 Если компилятор обнаруживает использование нерекомендуемого идентификатора или стандартные [ `[[deprecated]]` ](attributes.md) атрибут, [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) выдается предупреждение.  
  
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
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)