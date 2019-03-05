---
title: Классы простых типов данных
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: 4e415805301d7d12bd418a3b55509a7732851492
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298482"
---
# <a name="simple-data-type-classes"></a>Классы простых типов данных

Следующие классы инкапсулируют координаты рисования, символьных строк и время, и сведения о дате, что позволяет удобно использовать синтаксис C++. Эти объекты широко используются в качестве параметров для функций-членов классов Windows в библиотеке классов. Так как `CPoint`, `CSize`, и `CRect` соответствуют **ТОЧКИ**, **размер**, и **RECT** структуры, соответственно, в состав Windows SDK объекты этих классов C++ можно использовать везде, где можно использовать эти структуры языка. Классы предоставляют полезные интерфейсы через их функции-члены. `CStringT` предоставляет очень гибкие динамический символ строки. `CTime`, `COleDateTime`, `CTimeSpan`, и `COleTimeSpan` представления значений даты и времени. Дополнительные сведения об этих классах см. в статье [даты и времени](../atl-mfc-shared/date-and-time.md).

Классы, которые начинаются с "`COle`", межсетевые экраны, типов данных, предоставляемые OLE. Эти типы данных можно использовать в программах Windows независимо от того, используются ли другие функции OLE.

[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Содержит символьные строки.

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Содержит абсолютные значения даты и времени.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Оболочка для типа автоматизации OLE **даты**. Представляет значения даты и времени.

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Содержит относительный значения даты и времени.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
Содержит относительный `COleDateTime` значения, такие как разницу между двумя `COleDateTime` значения.

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Содержит пары координат (x, y).

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Содержит расстояние, относительные позиции или пар значений.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Содержит координаты прямоугольной области.

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Предоставляет функциональные возможности списка изображений Windows. Списки изображений используются с элементами управления списка и дерева элементов управления. Они также можно сохранить и заархивировать набора же разрядности точечных рисунков.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Оболочка для типа автоматизации OLE **VARIANT**. Данные в **VARIANT**s могут храниться в нескольких форматах.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Оболочка для типа автоматизации OLE **валюты**, с фиксированной запятой арифметический тип, с 15 цифр перед десятичной запятой и 4 цифры после.

> [!NOTE]
>  `CRect`, `CSize`, и `CPoint` могут использоваться в приложениях ATL или MFC. Кроме того `CStringT` предоставляет независимый MFC `CString`-как класс. Дополнительные сведения о классах служебной программы см. в разделе [общих классов](../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
