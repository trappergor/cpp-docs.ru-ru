---
title: устаревшие (C/C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
dev_langs:
- C++
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2280d5245292625bfc29815475eaca63d4d500bd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839823"
---
# <a name="deprecated-cc"></a>deprecated (C/C++)
**Устаревшими** директивы pragma можно указать, что функции, тип и другие идентификаторы могут не поддерживаться в будущем выпуске или больше не может использоваться.  
> [!NOTE]
> Сведения о C ++ 14 `[[deprecated]]` атрибут и рекомендации по использованию, vs Microsoft declspec или pragma см. в разделе [стандартные атрибуты C++](../cpp/attributes.md) атрибута.
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>Примечания  
 Когда компилятор встречает идентификатора, указанного **устаревшими** pragma, он выдает предупреждение компилятора [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).   
  
 Имена макросов можно объявить нерекомендуемыми. Поместите имя макроса в кавычки; в противном случае произойдет расширение макроса.  
  
 Поскольку **устаревшими** директивы pragma и работает на всех сопоставления идентификаторов, учитывает подписи, он не является лучшим вариантом для исключения устаревшего конкретных версий перегруженных функций. Все сопоставления имени функции добавлены в область действия срабатывает предупреждение.

  Мы рекомендуем использовать C ++ 14 `[[deprecated]]` атрибут, по возможности вместо **устаревшими** pragma. Майкрософт [__declspec(deprecated)](../cpp/deprecated-cpp.md) модификатора объявления также является более предпочтительной, во многих случаях, чем **устаревшими** pragma. `[[deprecated]]` Атрибута и `__declspec(deprecated)` модификатор позволяют определить нерекомендуемое состояние для отдельных форм перегруженных функций. Предупреждение диагностики отображается только для ссылок на конкретных перегруженной функции атрибут или модификатор применяется к.  
  
## <a name="example"></a>Пример  
  
```  
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
  
```  
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