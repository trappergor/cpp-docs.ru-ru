---
title: "code_seg (__declspec) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "code_seg_cpp"
  - "code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg __declspec - ключевое слово"
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# code_seg (__declspec)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Атрибут объявления `code_seg` называет исполняемый сегмент текста в obj\-файле, в котором будет храниться объектный код для этой функции или функций члена класса.  
  
## Синтаксис  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## Заметки  
 Атрибут `__declspec(code_seg(...))` позволяет помещать код в различные именованные сегменты, которые можно выгружать или блокировать в памяти по отдельности.  Можно использовать этот атрибут для управления размещением шаблонов с созданными экземплярами и кода, созданного компилятором.  
  
 *Сегмент* представляет собой блок данных в obj\-файле, который загружается в память как одно целое.  *Сегмент текста* — сегмент, содержащий исполняемый код.  Термин *раздел* часто используется вместо термина "сегмент", и наоборот.  
  
 Объектный код, создаваемый при определении `declarator`, помещается в сегмент текста, указанный `segname`, а это узкий строковый литерал.  Не требуется указывать имя `segname` в директиве pragma [section](../preprocessor/section.md) перед использованием в объявлении.  По умолчанию если значение `code_seg` не указано, объектный код помещается в сегмент с именем .text.  Атрибут `code_seg` переопределяет любую существующую директиву [\#pragma code\_seg](../preprocessor/code-seg.md).  Атрибут `code_seg`, примененный к функции\-члену, переопределяет любой атрибут `code_seg`, примененный к внешнему классу.  
  
 Если сущность имеет атрибут `code_seg`, все объявления и определения одной сущности должны иметь одинаковые атрибуты `code_seg`.  Если базовый класс имеет атрибут `code_seg`, производные классы должны иметь тот же атрибут.  
  
 Если атрибут `code_seg` применяется к функции в области пространства имен или функции\-члену, объектный код для этой функции помещается в указанный сегмент текста.  Если этот атрибут применяется к классу, все функции\-члены класса и вложенные классы, включая созданные компилятором специальные функции члены, помещаются в указанный сегмент.  Локально определенные классы, например классы, определенные в теле функции\-члена, не наследуют атрибут `code_seg` внешней области видимости.  
  
 Если атрибут `code_seg` применяется к шаблонному классу или шаблонной функции, все неявные специализации шаблона помещаются в указанный сегмент.  Явные и частичные специализации не наследуют атрибут `code_seg` из первичного шаблона.  Можно определить тот же или другой атрибут `code_seg` для специализации.  Атрибут `code_seg` не может применяться к явному созданию экземпляра шаблона.  
  
 По умолчанию созданный компилятором, такой как специальная функция\-член, помещается в сегмент .text.  Директива `#pragma code_seg` не переопределяет это значение по умолчанию.  Используйте атрибут `code_seg` для класса, шаблона класса или шаблона функции в целях управления тем, куда помещается созданный компилятором код.  
  
 Лямбда\-выражения наследуют атрибуты `code_seg` из своей внешней области видимости.  Для определения сегмента для лямбда\-выражения примените атрибут `code_seg` после предложения объявления параметра и перед всеми изменяемыми значениями и спецификациями исключений, всеми конечными спецификациями возвращаемого типа и телами лямбда\-выражений.  Для получения дополнительной информации см. [Синтаксис лямбда\-выражений](../cpp/lambda-expression-syntax.md).  В этом примере определяется лямбда\-выражение в сегменте с именем PagedMem:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Будьте внимательны при помещении определенных функций\-членов, особенно виртуальных функций\-членов, в разные сегменты.  При определении виртуальной функции в производном классе, находящемся в выгруженном сегменте, когда метод базового класса находится в невыгруженном в сегменте, другие методы базового класса или пользовательский код могут предположить, что вызов виртуального метода не активирует ошибку выгрузки.  
  
## Пример  
 В этом примере демонстрируется, как атрибут `code_seg` управляет размещением сегмента при использовании явной и неявной специализации шаблона:  
  
```  
// code_seg.cpp  
// Compile: cl /EHsc /W4 code_seg.cpp  
  
// Base template places object code in Segment_1 segment  
template<class T>  
class __declspec(code_seg("Segment_1")) Example  
{  
public:  
   virtual void VirtualMemberFunction(T /*arg*/) {}  
};  
  
// bool specialization places code in default .text segment  
template<>  
class Example<bool>   
{  
public:  
   virtual void VirtualMemberFunction(bool /*arg*/) {}  
};  
  
// int specialization places code in Segment_2 segment  
template<>  
class __declspec(code_seg("Segment_2")) Example<int>   
{  
public:  
   virtual void VirtualMemberFunction(int /*arg*/) {}  
};  
  
// Compiler warns and ignores __declspec(code_seg("Segment_3"))  
// in this explicit specialization  
__declspec(code_seg("Segment_3")) Example<short>; // C4071  
  
int main()  
{  
   // implicit double specialization uses base template's  
   // __declspec(code_seg("Segment_1")) to place object code  
   Example<double> doubleExample{};  
   doubleExample.VirtualMemberFunction(3.14L);  
  
   // bool specialization places object code in default .text segment  
   Example<bool> boolExample{};  
   boolExample.VirtualMemberFunction(true);  
  
   // int specialization uses __declspec(code_seg("Segment_2"))  
   // to place object code  
   Example<int> intExample{};  
   intExample.VirtualMemberFunction(42);  
}  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)