---
title: Интеграция со средой CLR (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: 44ef35d1a62706cae37285c06547a8b9b7deb35c
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740297"
---
# <a name="clr-integration-ccx"></a>Интеграция со средой CLR (C++/CX)

Некоторые типы среда выполнения Windows получают специальную обработку C++в языке/CX и языки, основанные на среде CLR. В этой статье рассматривается сопоставление определенных типов в одном языке с другим языком. Например, среда CLR сопоставляет Windows.Foundation.IVector с System.Collections.IList, Windows.Foundation.IMap с System.Collections.IDictionary и т. д. Аналогичным C++образом,/CX имеет такие типы карт, как platform::D делегата и Platform:: String.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Сопоставление среда выполнения Windows и C++/CX

Когда C++/CX считывает файл метаданных Windows (. winmd), компилятор автоматически сопоставляет общие среда выполнения Windows пространства имен и типы с C++типами и пространствами имен/CX. Например, числовой тип `UInt32` среда выполнения Windows автоматически сопоставляется с. `default::uint32`

C++/CX сопоставляет несколько других типов среда выполнения Windows с пространством имен **Platform** . Например, обработчик **Windows:: Foundation** HString, представляющий текстовую строку в Юникоде, доступную только для чтения, сопоставляется с C++классом/CX `Platform::String` . Если операция среда выполнения Windows возвращает ошибку HRESULT, она сопоставляется с C++/CX. `Platform::Exception`

Объект C++/CX также сопоставляет определенные типы в среда выполнения Windows пространствах имен, чтобы расширить функциональные возможности типа. Для этих типов класс C++/CX предоставляет вспомогательные конструкторы и методы, которые относятся к C++ и недоступны в стандартном файле. winmd типа.

В следующих списках приведены структуры значений, поддерживающие новые конструкторы и вспомогательные методы. Если ранее вы написали код, использующий списки инициализации структуры, измените его, чтобы применить новые конструкторы.

**Windows::Foundation**

- Точка

- Rect

- Size

**Windows::UI**

- Цвет

**Windows::UI::Xaml**

- CornerRadius

- Продолжительность

- GridLength

- Thickness

**Windows::UI::Xaml::Interop**

- TypeName

**Windows::UI::Xaml::Media**

- Матрица

**Windows::UI::Xaml::Media::Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>Сопоставление CLR и C++/CX

Когда Microsoft C++ или C# компиляторы считывают WINMD-файл, они автоматически сопоставляют определенные типы в файле метаданных с СООТВЕТСТВУЮЩИМИ C++типами/CX или CLR. Например, в CLR интерфейс IVector\<t > сопоставляется с IList\<t >. Но в C++языке/CX интерфейс IVector\<T > не сопоставлен с другим типом.

Иреференце\<t > в среда выполнения Windows сопоставляется со значением\<Nullable t > в .NET.

## <a name="see-also"></a>См. также

[Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)
