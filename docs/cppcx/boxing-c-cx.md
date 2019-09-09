---
title: Упаковка-преобразование (C++/CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 90c5af31efc6523683227dbf54c85390bc98510a
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740664"
---
# <a name="boxing-ccx"></a>Упаковка-преобразование (C++/CX)

*Упаковка* — это заключение переменной типа значения, например [Windows::Foundation::DateTime](/uwp/api/windows.foundation.datetime), или базового скалярного типа, например `int`, в ссылочный класс при передаче переменной методу, который в качестве входного типа принимает [Platform::Object^](../cppcx/platform-object-class.md) .

## <a name="passing-a-value-type-to-an-object-parameter"></a>Передача типа значения параметру Object^

Хотя явным образом упаковывать переменную для ее передачи в параметр метода типа [Platform::Object^](../cppcx/platform-object-class.md)не требуется, необходимо выполнять явное приведение к исходному типу при получении значений, которые до этого были упакованы.

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Использование Platform:: ibox\<T > для поддержки типов значений, допускающих значения NULL

C# и Visual Basic поддерживают понятие типов значений, допускающих значения null. В C++языке/CX можно использовать `Platform::IBox<T>` тип для предоставления открытых методов, поддерживающих параметры типа значения, допускающие значение null. В следующем примере показан открытый C++метод/CX, возвращающий значение NULL C# , если вызывающий объект передает значение NULL для одного из аргументов.

[!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]

В клиенте XAML C# его можно использовать следующим образом:

```

// C# client code
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();
    int? a = null;
    int? b = 5;
    var result = obj.Multiply(a,b); //result = null
```

## <a name="see-also"></a>См. также

[Система типов (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Приведение (C++/CX)](../cppcx/casting-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
