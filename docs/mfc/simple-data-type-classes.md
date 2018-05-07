---
title: Классы простых типов данных | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54d7f200ee35489f37256023d28bdd3260bf48ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="simple-data-type-classes"></a>Классы простых типов данных
Следующие классы инкапсулируют рисования координат, символьных строк и время, и сведения о дате, что позволяет удобным использовать синтаксис C++. Эти объекты широко используются в качестве параметров для функции-члены классов Windows в библиотеке классов. Поскольку `CPoint`, `CSize`, и `CRect` соответствуют **ТОЧКИ**, **размер**, и `RECT` структур, соответственно, в Windows SDK, можно использовать объекты из них Везде, где можно использовать эти структуры языка C, классы C++. Классы предоставляют полезные интерфейсов с помощью функций-членов. `CStringT` предоставляет очень гибкие динамический символ строки. `CTime`, `COleDateTime`, `CTimeSpan`, и **COleTimeSpan** представления значений даты и времени. Дополнительные сведения об этих классах см. в статье [даты и времени](../atl-mfc-shared/date-and-time.md).  
  
 Классы, которые начинаются с «**COle**» являются encapsulations типов данных, предоставляемых OLE. Эти типы данных можно использовать в приложениях Windows, независимо от того, используются ли другие функции OLE.  
  
 [Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Содержит строки символов.  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 Содержит абсолютный значения даты и времени.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Программа-оболочка для типа автоматизации OLE **даты**. Представляет значения даты и времени.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 Содержит значения даты и времени.  
  
 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 Содержит относительный `COleDateTime` значения, такие как разницу между двумя `COleDateTime` значения.  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Хранит пары координат (x, y).  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Содержит расстояние, относительные позиции или пар значений.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Содержит координаты прямоугольной области.  
  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Предоставляет функции списка изображений Windows. Списки изображений используются элементы управления списка и дерева. Они также могут использоваться для хранения и архивирования набора точечных рисунков, аналогичного размера.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Программа-оболочка для типа автоматизации OLE **VARIANT**. Данные в **VARIANT**s могут храниться в нескольких форматов.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Программа-оболочка для типа автоматизации OLE **валюты**, с фиксированной запятой арифметический тип с 15 цифр перед десятичной запятой и 4 цифры после.  
  
> [!NOTE]
>  `CRect`, `CSize`, и `CPoint` могут использоваться в приложениях ATL и MFC. Кроме того `CStringT` предоставляет независимый MFC `CString`— как и класс. Дополнительные сведения об общих служебных классов см. в разделе [совместно используемые классы](../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

