---
title: "code_seg (__declspec) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- code_seg_cpp
dev_langs:
- C++
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 242dfa36d3cd0c28d1feeb2bd4a2c41d29220b40
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="codeseg-declspec"></a>code_seg (__declspec)
**Блок, относящийся только к системам Майкрософт**  
  
 Атрибут объявления `code_seg` называет исполняемый сегмент текста в obj-файле, в котором будет храниться объектный код для этой функции или функций члена класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## <a name="remarks"></a>Примечания  
 Атрибут `__declspec(code_seg(...))` позволяет помещать код в различные именованные сегменты, которые можно выгружать или блокировать в памяти по отдельности. Можно использовать этот атрибут для управления размещением шаблонов с созданными экземплярами и кода, созданного компилятором.  
  
 Объект *сегмент* представляет собой именованный блок данных в OBJ-файле, который загружается в память как одно целое. Объект *сегмент текста* — сегмент, содержащий исполняемый код. Термин *раздел* часто взаимозаменяемы с сегментом.  
  
 Объектный код, создаваемый при определении `declarator`, помещается в сегмент текста, указанный `segname`, а это узкий строковый литерал. Имя `segname` не должен быть указан в [раздел](../preprocessor/section.md) pragma, прежде чем он может использоваться в объявлении. По умолчанию если значение `code_seg` не указано, объектный код помещается в сегмент с именем .text. Объект `code_seg` атрибут переопределяет любую существующую [#pragma code_seg](../preprocessor/code-seg.md) директивы. Атрибут `code_seg`, примененный к функции-члену, переопределяет любой атрибут `code_seg`, примененный к внешнему классу.  
  
 Если сущность имеет атрибут `code_seg`, все объявления и определения одной сущности должны иметь одинаковые атрибуты `code_seg`. Если базовый класс имеет атрибут `code_seg`, производные классы должны иметь тот же атрибут.  
  
 Если атрибут `code_seg` применяется к функции в области пространства имен или функции-члену, объектный код для этой функции помещается в указанный сегмент текста. Если этот атрибут применяется к классу, все функции-члены класса и вложенные классы, включая созданные компилятором специальные функции члены, помещаются в указанный сегмент. Локально определенные классы, например классы, определенные в теле функции-члена, не наследуют атрибут `code_seg` внешней области видимости.  
  
 Если атрибут `code_seg` применяется к шаблонному классу или шаблонной функции, все неявные специализации шаблона помещаются в указанный сегмент. Явные и частичные специализации не наследуют атрибут `code_seg` из первичного шаблона. Можно определить тот же или другой атрибут `code_seg` для специализации. Атрибут `code_seg` не может применяться к явному созданию экземпляра шаблона.  
  
 По умолчанию созданный компилятором, такой как специальная функция-член, помещается в сегмент .text. Директива `#pragma code_seg` не переопределяет это значение по умолчанию. Используйте атрибут `code_seg` для класса, шаблона класса или шаблона функции в целях управления тем, куда помещается созданный компилятором код.  
  
 Лямбда-выражения наследуют атрибуты `code_seg` из своей внешней области видимости. Для определения сегмента для лямбда-выражения примените атрибут `code_seg` после предложения объявления параметра и перед всеми изменяемыми значениями и спецификациями исключений, всеми конечными спецификациями возвращаемого типа и телами лямбда-выражений. Дополнительные сведения см. в разделе [синтаксис лямбда-выражений](../cpp/lambda-expression-syntax.md). В этом примере определяется лямбда-выражение в сегменте с именем PagedMem:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Будьте внимательны при помещении определенных функций-членов, особенно виртуальных функций-членов, в разные сегменты. При определении виртуальной функции в производном классе, находящемся в выгруженном сегменте, когда метод базового класса находится в невыгруженном в сегменте, другие методы базового класса или пользовательский код могут предположить, что вызов виртуального метода не активирует ошибку выгрузки.  
  
## <a name="example"></a>Пример  
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
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
