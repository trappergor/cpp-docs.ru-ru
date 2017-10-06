---
title: "устаревшие (C++) | Документы Microsoft"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- deprecated_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9ac25648e2d19da82f6c213992699c237e05c01e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="deprecated-c"></a>deprecated (C++)
Этот раздел посвящен Майкрософт рекомендуется к использованию declspec объявления. Сведения о C ++ 14 `[[deprecated]]` атрибут и рекомендации по использованию этого атрибута и declspec характерные для Майкрософт или директивы pragma в разделе [стандартные атрибуты C++](attributes2.md).

 За исключением указанных ниже **устаревшими** объявление предоставляет те же возможности, как [устаревшими](../preprocessor/deprecated-c-cpp.md) директивы pragma:  
  
-   **Устаревшими** объявление позволяет указать определенные формы перегрузок функций как нерекомендуемые, тогда как форма директивы pragma применяется ко всем перегруженным формам имени функции.  
  
-   **Устаревшими** объявление позволяет указать сообщение, которое будет отображаться во время компиляции. Текст сообщения может быть взят из макроса.  
  
-   Макросы только могут быть помечены как устаревшие с **устаревшими** pragma.  
  
 Если компилятор обнаруживает использование нерекомендуемого идентификатора или стандарт [ `[[deprecated]]` ](attributes2.md) атрибута [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) выдается предупреждение.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отметить функции как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемая функция.  
  
```  
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
  
```  
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
