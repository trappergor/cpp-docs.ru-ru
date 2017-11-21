---
title: "Контекстные ключевые слова (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: internal_CPP
dev_langs: C++
helpviewer_keywords: context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68ff63d5b596d575f26ec0f56a3ac7a568c8471e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>Контекстные ключевые слова (расширения компонентов C++)
*Контекстные ключевые слова* – это языковые элементы, которые распознаются только в определенном контексте. Вне указанного контекста они могут быть символами, которые определяются пользователем.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Заметки**  
  
 Ниже приведен список контекстно-зависимых ключевых слов:  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [литерал](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [Свойство](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where`(часть [универсальных шаблонов](../windows/generics-cpp-component-extensions.md))  
  
 Для повышения удобочитаемости можно ограничить использование контекстно-зависимые ключевые слова как символов, определенных пользователем.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 **Заметки**  
  
 (Отсутствуют комментарии для данной возможности в рамках этой платформы).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 (Отсутствуют комментарии для данной возможности в рамках этой платформы).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода показано, что в соответствующем контексте контекстно-зависимое ключевое слово `property` можно использовать для определения свойства и переменной.  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **Вывод**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)