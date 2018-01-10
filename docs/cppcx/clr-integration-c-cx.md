---
title: "Интеграция со средой CLR (C + +/ CX) | Документы Microsoft"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9851a7aa0d1dad84a37504b479c551ffa63bcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clr-integration-ccx"></a>Интеграция со средой CLR (C++/CX)
Некоторые типы среды выполнения Windows получают специальную обработку в C + +/ CX и языки, которые основаны на среде (CLR). В этой статье рассматривается сопоставление определенных типов в одном языке с другим языком. Например, среда CLR сопоставляет Windows.Foundation.IVector с System.Collections.IList, Windows.Foundation.IMap с System.Collections.IDictionary и т. д. Аналогичным образом, C + +/ CX специально сопоставляет такие типы, такие как Platform::Delegate и Platform::String.  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Сопоставление среды выполнения Windows на C + +/ CX  
 Когда C + +/ CX считывает файл метаданных Windows (winmd), компилятор автоматически сопоставляет общие пространства имен среды выполнения Windows и типы C + +/ CX пространств имен и типов. Например, числовой тип среды выполнения Windows `UInt32` автоматически сопоставляется с `default::uint32`.  
  
 C + +/ CX сопоставляет несколько других типов среды выполнения Windows для **платформы** пространства имен. Например **Windows::Foundation** HSTRING дескриптора, который представляет доступный только для чтения текстовую строку Юникода, сопоставляется C + +/ CX `Platform::String` класса. При выполнении операции среды выполнения Windows возвращает ошибку HRESULT, он сопоставляется C + +/ CX `Platform::Exception`. Для получения дополнительной информации см. [Built-in Types](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 C + +/ CX также сопоставляет определенные типы в пространствах имен среды выполнения Windows, чтобы расширить функциональные возможности типа. Для этих типов C + +/ CX предоставляет вспомогательные конструкторы и методы, относящиеся к C++ и не доступны в стандартном winmd-файле этого типа.  
  
 В следующих списках приведены структуры значений, поддерживающие новые конструкторы и вспомогательные методы. Если ранее вы написали код, использующий списки инициализации структуры, измените его, чтобы применить новые конструкторы.  
  
 **Windows::Foundation**  
  
-   Точка  
  
-   Rect  
  
-   Размер  
  
 **Windows::UI**  
  
-   Цвет  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   Длительность  
  
-   GridLength  
  
-   Thickness  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   Матрица  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## <a name="mapping-the-clr-to-ccx"></a>Сопоставление среды CLR для C + +/ CX  
 Когда компиляторы Visual C++ или C# прочитать файл winmd, они автоматически сопоставляют определенные типы в файле метаданных до соответствующих C + +/ CX или CLR типов. Например, в среде CLR, IVector\<T > интерфейс сопоставляется с IList\<T >. Однако в C + +/ CX, IVector\<T > интерфейса не сопоставляется с другим типом.  
  
 IReference\<T > в среде выполнения Windows, сопоставляется с Nullable\<T > в .NET.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)