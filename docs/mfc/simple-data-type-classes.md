---
title: "Классы простых типов данных | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы данных [C++]"
  - "скалярные классы [C++]"
  - "классы простых типов данных"
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Классы простых типов данных
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы инкапсулируют координаты рисования, символьные строки, и сведения о дате и времени, что позволяет удобным C помощью синтаксиса C\+\+.  Эти объекты часто используются в качестве параметров к функциям элемента Windows классов в библиотеке классов.  Поскольку `CPoint`, `CSize` и `CRect` соответствуют **POINT**, **SIZE** и структур `RECT` соответственно, в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] можно использовать объекты этих классов C\+\+ для них можно использовать эти структуры языка C\#.  Классы предоставляют необходимые интерфейсы посредством их функции\-члены.  `CStringT` предоставляет очень гибкие динамических строк символов.  `CTime`, `COleDateTime`, `CTimeSpan` и **COleTimeSpan** представляют значения времени и даты.  Дополнительные сведения о этих классов см. в статье [Дата и время](../atl-mfc-shared/date-and-time.md).  
  
 Классы, которые начинаются с «**COle**» инкапсуляции типов данных, передаваемых OLE.  Эти типы данных можно использовать в программах на Windows независимо от того, используются ли другие функции OLE.  
  
 [Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Содержит символьные строки.  
  
 [CTime](../Topic/CTime%20Class.md)  
 Содержит абсолютные значения времени и даты.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Программа\-оболочка для типа **date** ole\-автоматизации.  Представляет значения даты и времени.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 Содержит относительных значений времени и даты.  
  
 [COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md)  
 Содержит относительные значения `COleDateTime`, например разницу между значениями 2 `COleDateTime`.  
  
 [CPoint](../Topic/CPoint%20Class.md)  
 Содержит пары координаты \(x, y\).  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Содержит расстояние, относительные позиции, или пары значений.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Содержит координаты прямоугольных области.  
  
 [CImageList](../Topic/CImageList%20Class.md)  
 Предоставляет функциональные возможности списка изображение Windows.  Списки изображений используются с элементами управления списка и элементами управления дерева.  Их также можно использовать для хранения и архивируйте набор в том же измененных размер растровые изображения.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Программа\-оболочка для типа **VARIANT** ole\-автоматизации.  Данные в **VARIANT**, можно хранить в несколько форматов.  
  
 [COleCurrency](../Topic/COleCurrency%20Class.md)  
 Программа\-оболочка для типа **CURRENCY** ole\-автоматизации, с фиксированной запятой арифметического типа, с 15 цифрами перед десятичной запятой и 4 цифр позже.  
  
> [!NOTE]
>  Начиная с Visual C\+\+ .NET C, `CRect`, `CSize` и `CPoint` модифицировались использоваться в приложениях или ATL или MFC.  Кроме того, `CStringT` добавлено для предоставления образце не зависит от класса `CString` похожий на.  Дополнительные сведения об общих служебных классов см. в разделе [Общие классы](../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)