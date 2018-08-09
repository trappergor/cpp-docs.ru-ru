---
title: Контекстные ключевые слова (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e362ec513cb7cb14f5fd3abb8a028c6e0eab616b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644233"
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>Контекстные ключевые слова (расширения компонентов C++)
*Контекстные ключевые слова* — это языковые элементы, которые распознаются только в определенных контекстах. Вне указанного контекста они могут быть символами, которые определяются пользователем.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
### <a name="remarks"></a>Примечания
  
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
  
-   [свойство](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where` (частью [универсальные шаблоны](../windows/generics-cpp-component-extensions.md))  
  
 Для повышения удобочитаемости можно ограничить использование контекстно-зависимые ключевые слова как символы, определяемые пользователем.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
### <a name="remarks"></a>Примечания  
  
 (Отсутствуют комментарии для данной возможности в рамках этой платформы).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: `/ZW`  
  
## <a name="common-language-runtime"></a>Среда CLR 
### <a name="remarks"></a>Примечания  
  
 (Отсутствуют комментарии для данной возможности в рамках этой платформы).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: `/clr`  
  
### <a name="examples"></a>Примеры  
  
 В следующем примере кода показано, что в соответствующем контексте **свойство** контекстно-зависимые ключевое слово может использоваться для определения свойства и переменной.  
  
```cpp  
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
  
```Output  
100  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)