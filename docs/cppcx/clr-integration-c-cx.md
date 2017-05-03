---
title: "Интеграция со средой CLR (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Интеграция со средой CLR (C++/CX)
Некоторые типы [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] получают специальную обработку в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] и языки, которые основаны на среде CLR. В этой статье рассматривается сопоставление определенных типов в одном языке с другим языком. Например, среда CLR сопоставляет Windows.Foundation.IVector с System.Collections.IList, Windows.Foundation.IMap с System.Collections.IDictionary и т. д. Аналогично, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] специально сопоставляет такие типы, как Platform::Delegate и Platform::String.  
  
## Сопоставление [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] с [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Когда [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] считывает файл метаданных Windows \(WINMD\-файл\), компилятор автоматически сопоставляет общие пространства имен и типы [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] с пространствами имен и типами [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Например, числовой тип `UInt32` [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] автоматически сопоставляется с `default::uint32`.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] сопоставляет несколько других типов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] с пространством имен **Platform**. Например, дескриптор HSTRING **Windows::Foundation**, который представляет доступную только для чтения текстовую строку Юникода, сопоставляется с классом `Platform::String` [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Когда операция [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] возвращает ошибку HRESULT, она сопоставляется с `Platform::Exception` [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Для получения дополнительной информации см. [Built\-in Types](http://msdn.microsoft.com/ru-ru/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] также сопоставляет определенные типы в пространствах имен [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], чтобы расширить функциональность типа. Для этих типов [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] предоставляет вспомогательные конструкторы и методы, относящиеся к C\+\+ и не доступные в стандартном WINMD\-файле этого типа.  
  
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
  
## Сопоставление среды CLR с [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Когда компиляторы Visual C\+\+ или C\# читают WINMD\-файл, они автоматически сопоставляют определенные типы в этом файле метаданных с соответствующими типами [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] или среды CLR. Например, в среде CLR интерфейс IVector\<T\> сопоставляется с IList\<T\>. Однако в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] интерфейс IVector\<T\> не сопоставляется с другим типом.  
  
 IReference\<T\> в [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] сопоставляется с Nullable\<T\> в .NET.  
  
## См. также  
 [Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)