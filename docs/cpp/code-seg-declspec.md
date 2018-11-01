---
title: code_seg (__declspec)
ms.date: 11/04/2016
f1_keywords:
- code_seg_cpp
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
ms.openlocfilehash: a0b9c6dcd7ee19af59ac39a71498fe41bfc107ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506903"
---
# <a name="codeseg-declspec"></a>code_seg (__declspec)

**Блок, относящийся только к системам Microsoft**

**Code_seg** атрибут объявления называет исполняемый сегмент текста в OBJ-файле, в которой будет храниться объектный код для функции или функции-члены класса.

## <a name="syntax"></a>Синтаксис

```
__declspec(code_seg("segname")) declarator
```

## <a name="remarks"></a>Примечания

Атрибут `__declspec(code_seg(...))` позволяет помещать код в различные именованные сегменты, которые можно выгружать или блокировать в памяти по отдельности. Можно использовать этот атрибут для управления размещением шаблонов с созданными экземплярами и кода, созданного компилятором.

Объект *сегмент* представляет собой именованный блок данных в OBJ-файле, который загружается в память как одно целое. Объект *сегмент текста* сегмент, содержащий исполняемый код. Термин *разделе* часто используется вместо термина с сегментом.

Объектный код, создаваемый при определении `declarator`, помещается в сегмент текста, указанный `segname`, а это узкий строковый литерал. Имя `segname` не должно быть задано в [разделе](../preprocessor/section.md) директивы pragma, прежде чем он может использоваться в объявлении. По умолчанию если значение `code_seg` не указано, объектный код помещается в сегмент с именем .text. Объект **code_seg** атрибут переопределяет любую существующую [#pragma code_seg](../preprocessor/code-seg.md) директива. Объект **code_seg** атрибут, примененный к функции-члена переопределяет все **code_seg** атрибут, примененный к включающего класса.

Если у сущности есть **code_seg** атрибута, все объявления и определения одной сущности должны иметь одинаковые **code_seg** атрибуты. Если базовый класс имеет **code_seg** атрибут, производные классы должны иметь тот же атрибут.

Когда **code_seg** атрибут применяется к функции области пространства имен или функции-члену, объектный код для этой функции помещается в указанный сегмент текста. Если этот атрибут применяется к классу, все функции-члены класса и вложенные классы, включая созданные компилятором специальные функции члены, помещаются в указанный сегмент. Локально определенные классы — например, классы, определенные в теле функции-члена, не наследуют **code_seg** атрибут внешней области видимости.

Когда **code_seg** атрибут применяется к шаблонному классу или функция шаблона, все неявные специализации шаблона помещаются в указанный сегмент. Явные и частичные специализации не наследуют **code_seg** атрибут из первичного шаблона. Можно указать тот же или другой **code_seg** атрибут для специализации. Объект **code_seg** атрибут не может использоваться для явному созданию экземпляра шаблона.

По умолчанию созданный компилятором, такой как специальная функция-член, помещается в сегмент .text. Директива `#pragma code_seg` не переопределяет это значение по умолчанию. Используйте **code_seg** атрибут класса, шаблон класса или функции-шаблона к элементу управления, где помещается созданный компилятором код.

Лямбда-выражения наследуют **code_seg** атрибуты из своей внешней области видимости. Для определения сегмента для лямбда-выражения, примените **code_seg** атрибут после предложения объявления параметра и перед всеми изменяемыми или спецификация исключений, все конечные спецификации типа возвращаемого значения и тело лямбда-выражения. Дополнительные сведения см. в разделе [синтаксис лямбда-выражений](../cpp/lambda-expression-syntax.md). В этом примере определяется лямбда-выражение в сегменте с именем PagedMem:

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

Будьте внимательны при помещении определенных функций-членов, особенно виртуальных функций-членов, в разные сегменты. При определении виртуальной функции в производном классе, находящемся в выгруженном сегменте, когда метод базового класса находится в невыгруженном в сегменте, другие методы базового класса или пользовательский код могут предположить, что вызов виртуального метода не активирует ошибку выгрузки.

## <a name="example"></a>Пример

В этом примере показано, как **code_seg** атрибута управляет размещением сегмента при неявных и явной специализации шаблона используется:

```cpp
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

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)