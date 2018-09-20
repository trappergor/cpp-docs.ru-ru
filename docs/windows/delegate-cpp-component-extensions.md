---
title: Delegate (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
dev_langs:
- C++
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13ce7d2a35245716adc70b9e84532ea7d1a4a440
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432416"
---
# <a name="delegate--c-component-extensions"></a>delegate (расширения компонентов C++)

Объявляет тип, представляющий указатель на функцию.

## <a name="all-runtimes"></a>Все среды выполнения

Среда выполнения Windows и среда CLR поддерживает делегаты.

### <a name="remarks"></a>Примечания

**Делегировать** является контекстно-зависимые ключевым словом. Дополнительные сведения см. в разделе [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).

Для обнаружения во время компиляции, если тип является делегатом, используйте `__is_delegate()` Признак типа. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Среда выполнения Windows

C + +/ CX поддерживает делегаты со следующим синтаксисом.

### <a name="syntax"></a>Синтаксис

```cpp
access
delegate
return-type
delegate-type-identifier
(
[ parameters ]
)  
```

### <a name="parameters"></a>Параметры

*access*<br/>
(необязательно) Доступность делегат, который может быть **открытый** (по умолчанию) или **частного**. Прототип функции также могут быть дополнены **const** или **volatile** ключевые слова.

*Тип возвращаемого значения*<br/>
Возвращаемый тип прототипа функции.

*идентификатор для типа делегата*<br/>
Имя типа объявленный делегат.

*Параметры*<br/>
(Необязательно) Типы и идентификаторы прототипа функции.

### <a name="remarks"></a>Примечания

Используйте *идентификатор для типа делегата* для объявления события с тот же прототип, что делегат. Дополнительные сведения см. в разделе [делегаты (C + +/ CX)](../cppcx/delegates-c-cx.md).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

Среда CLR поддерживает делегаты со следующим синтаксисом.

### <a name="syntax"></a>Синтаксис

```cpp
access
delegate
function_declaration
```

### <a name="parameters"></a>Параметры

*access*<br/>
(необязательно) Доступность делегата вне сборки может быть открытым или закрытым.  Значение по умолчанию является закрытым.  Внутри класса делегат может иметь любой уровень доступа.

*function_declaration*<br/>
Сигнатура функции, могут быть привязаны к делегату. Тип возвращаемого значения делегата может быть любой управляемый тип. По соображениям совместимости рекомендуется, тип возвращаемого значения делегата был типом CLS.

Для определения непривязанного делегата первый параметр в *function_declaration* должен быть типом значения **это** указатель для объекта.

### <a name="remarks"></a>Примечания

Делегаты являются многоадресными: «указатель на функцию» могут быть привязаны к один или несколько методов управляемого класса. **Делегировать** ключевое слово определяет тип многоадресного делегата с сигнатурой определенного метода.

Делегат также может быть привязан к метод класса значений, таких как статический метод.

Делегат имеет следующие характеристики:

- Он наследует от `System::MulticastDelegate`.

- Он имеет конструктор, который принимает два аргумента: указатель на управляемый класс или значение NULL (в случае привязки статическому методу) и полный метод указанного типа.

- Он содержит метод `Invoke`, сигнатура которого соответствует объявленной сигнатуре делегата.

При вызове делегата, его функции вызываются в порядке, в котором они были присоединены.

Возвращаемое значение делегата является возвращаемое значение из его последней присоединенного члена функции.

Делегаты не могут быть перегружены.

Делегаты можно привязать или отменить привязку.

При создании экземпляра делегата привязанного, первый аргумент должен быть ссылкой на объект. Второй аргумент функции создания экземпляра делегата должны либо быть адрес метода объекта управляемого класса, или указатель к методу типа значения. Второй аргумент функции создания экземпляра делегата необходимо имя метода с помощью синтаксиса область полный класс и применить оператор address-of.

При создании экземпляра несвязанного делегата, первый аргумент должен быть адрес метода объекта управляемого класса, или указатель на метод типа значения. Аргумент должен методу с помощью синтаксиса область полный класс имя и применить оператор взятия адреса.

При создании делегата статической или глобальной функции, необходим только один параметр: функция (при необходимости адрес функции).

Дополнительные сведения о делегатах см. в разделе

- [Практическое руководство. Определение и использование делегатов (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)

- [Универсальные делегаты (Visual C++)](../windows/generic-delegates-visual-cpp.md)

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

Приведенный ниже показано, как объявить и инициализировать вызова делегатов.

```cpp
// mcppv2_delegate.cpp
// compile with: /clr
using namespace System;

// declare a delegate
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      Console::WriteLine("in func1 {0}", i);
   }

   void func2(int i) {
      Console::WriteLine("in func2 {0}", i);
   }

   static void func3(int i) {
      Console::WriteLine("in static func3 {0}", i);
   }
};

int main () {
   A ^ a = gcnew A;

   // declare a delegate instance
   MyDel^ DelInst;

   // test if delegate is initialized
   if (DelInst)  
      DelInst(7);

   // assigning to delegate
   DelInst = gcnew MyDel(a, &A::func1);

   // invoke delegate
   if (DelInst)  
      DelInst(8);

   // add a function
   DelInst += gcnew MyDel(a, &A::func2);

   DelInst(9);

   // remove a function
   DelInst -= gcnew MyDel(a, &A::func1);

   // invoke delegate with Invoke
   DelInst->Invoke(10);

   // make delegate to static function
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);
   StaticDelInst(11);
}
```

```Output
in func1 8

in func1 9

in func2 9

in func2 10

in static func3 11
```

## <a name="see-also"></a>См. также

[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)