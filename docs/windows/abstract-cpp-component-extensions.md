---
title: abstract (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs:
- C++
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac043a76ab70c77bd8cdb3a2dd0c66498e409171
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463246"
---
# <a name="abstract--c-component-extensions"></a>abstract (расширения компонентов C++)
**Абстрактный** ключевое слово объявляет один из:  
  
-   Тип можно использовать в качестве базового типа, но экземпляр самого тип не может быть создан.  
  
-   Функция-член типа может определяться только в производном типе.  
  
## <a name="all-platforms"></a>Все платформы  
 **Синтаксис**  
  
```  
      class-declaration  
      class-identifier  
      abstract {}  
virtualreturn-typemember-function-identifier() abstract ;  
```  
  
 **Заметки**  
  
 В первом примере синтаксиса объявляется абстрактный класс. *Объявление класса* компонент может быть либо собственным объявлением C++ (**класс** или **структуры**), или объявлением расширения C++ (**ссылочного класса** или **структура ссылки**) Если `/ZW` или `/clr` был указан параметр компилятора.  
  
 Во втором примере синтаксиса объявляется абстрактная виртуальная функция-член. Объявление функции абстрактной — то же, что и объявление ее чистой виртуальной функцией. Объявление функции-члена абстрактной также приводит к тому, что включающий класс объявляется как абстрактный.  
  
 **Абстрактный** ключевое слово поддерживается в машинном и платформой коде; то есть, его можно скомпилировать с или без `/ZW` или `/clr` параметр компилятора.  
  
 Можно определить во время компиляции, если тип является абстрактным, с помощью `__is_abstract(type)` Признак типа. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 **Абстрактный** ключевое слово является описателем контекстно-зависимые переопределения. Дополнительные сведения о контекстно-зависимые ключевые слова, см. в разделе [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md). Дополнительные сведения об описателях переопределения см. в разделе [как: объявление спецификаторов переопределения в компиляциях машинного кода](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Дополнительные сведения см. в разделе [классы и структуры ссылки](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода возникает ошибка, поскольку класс `X` помечен как `abstract`.  
  
```cpp  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **Пример**  
  
 В следующем примере кода возникает ошибка, поскольку он создает экземпляр собственного класса, помеченного как `abstract`. Эта ошибка будет возникать как с параметром компилятора `/clr`, так и без него.  
  
```cpp  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
```  
  
 **Пример**  
  
 В следующем примере кода возникает ошибка, поскольку функция `f` включает определение, но помечена как `abstract`. Последняя инструкция в примере показывает, что объявление абстрактной виртуальной функции эквивалентно объявлению чистой виртуальной функции.  
  
```cpp  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)