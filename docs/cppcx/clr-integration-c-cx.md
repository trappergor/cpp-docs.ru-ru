---
title: Интеграция со средой CLR (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: df0c5e9cfaf9a4148c8d16b68ee04b4e9ce82e6a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749027"
---
# <a name="clr-integration-ccx"></a>Интеграция со средой CLR (C++/CX)

Некоторые типы среды выполнения Windows получают специальную обработку в C + +/ CX и языки, которые основаны на общеязыковой среды выполнения (CLR). В этой статье рассматривается сопоставление определенных типов в одном языке с другим языком. Например, среда CLR сопоставляет Windows.Foundation.IVector с System.Collections.IList, Windows.Foundation.IMap с System.Collections.IDictionary и т. д. Аналогичным образом, C + +/ CX специально сопоставляет такие типы, такие как Platform::Delegate и Platform::String.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Сопоставление среды выполнения Windows на C + +/ CX

Когда C + +/ CX считывает файл метаданных (с расширением winmd) Windows, компилятор автоматически сопоставляет общие пространства имен среды выполнения Windows и типы C + +/ CX пространств имен и типов. Например, числовой тип среды выполнения Windows `UInt32` автоматически сопоставляется с `default::uint32`.

C + +/ CX сопоставляет несколько других типов среды выполнения Windows, чтобы **платформы** пространства имен. Например **Windows::Foundation** дескриптор HSTRING, который представляет доступный только для чтения текстовую строку Юникода, сопоставляется C + +/ CX `Platform::String` класса. Когда операция среды выполнения Windows возвращает ошибку HRESULT, она сопоставляется C + +/ CX `Platform::Exception`.

C + +/ CX также сопоставляет определенные типы в пространствах имен среды выполнения Windows, чтобы расширить функциональность типа. Для этих типов C + +/ CX предоставляет вспомогательные конструкторы и методы, относящиеся к C++ и недоступны в стандартном winmd-файле этого типа.

В следующих списках приведены структуры значений, поддерживающие новые конструкторы и вспомогательные методы. Если ранее вы написали код, использующий списки инициализации структуры, измените его, чтобы применить новые конструкторы.

**Windows::Foundation**

- Точка

- Rect

- Размер

**Windows::UI**

- Цвет

**Windows::UI::Xaml**

- CornerRadius

- Длительность

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

## <a name="mapping-the-clr-to-ccx"></a>Сопоставление среды CLR для C + +/ CX

При чтении файла .winmd компиляторы Visual C++ или C# они автоматически сопоставляют определенные типы в файле метаданных для соответствующих C + +/ CX или CLR типов. Например, в среде CLR, IVector\<T > интерфейс сопоставляется с IList\<T >. Но в C + +/ CX, IVector\<T > интерфейс не сопоставлен с другим типом.

IReference\<T > в среде выполнения Windows сопоставляется с Nullable\<T > в .NET.

## <a name="see-also"></a>См. также

[Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)
