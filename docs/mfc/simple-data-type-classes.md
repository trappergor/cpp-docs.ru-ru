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
ms.openlocfilehash: d4038334e35b734370a437d35519498b96c00770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365403"
---
# <a name="simple-data-type-classes"></a>Классы простых типов данных

Следующие классы инкапсулируют координаты чертежа, строки символов, а также информацию о времени и дате, что позволяет удобно использовать синтаксис СЗ. Эти объекты широко используются в качестве параметров для функций членов классов Windows в библиотеке классов. `CPoint`Потому `CSize`что, и `CRect` соответствуют **POINT**, **СИЗЕ**, и **RECT** структур, соответственно, в Windows SDK, вы можете использовать объекты этих классов СЗ, где вы можете использовать эти C-языковые структуры. Классы предоставляют полезные интерфейсы через свои функции членов. `CStringT`обеспечивает очень гибкие динамические строки характера. `CTime`, `COleDateTime` `CTimeSpan`, `COleTimeSpan` и представляют значения времени и даты. Для получения дополнительной информации об этих классах, [см.](../atl-mfc-shared/date-and-time.md)

Классы, которые`COle`начинаются с " являются инкапсуляциями типов данных, предоставляемых OLE. Эти типы данных могут использоваться в программах Windows независимо от того, используются ли другие функции OLE.

[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Удерживает строки символов.

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Сохраняет абсолютные значения времени и даты.

[Coledatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Обертка для типа автоматизации OLE **DATE**. Представляет значения даты и времени.

[Ctimespan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Сохраняет относительные значения времени и даты.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
Сохраняет `COleDateTime` относительные значения, такие `COleDateTime` как разница между двумя значениями.

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Удерживает координаты (x, y) пары.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Сохраняет расстояние, относительные позиции или парные значения.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Сохраняет координаты прямоугольных областей.

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Обеспечивает функциональность списка изображений Windows. Списки изображений используются с элементами управления списками и элементами управления деревьями. Они также могут быть использованы для хранения и архивирования набора тожеразмерных битовых карт.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Обертка для типа автоматизации OLE **VARIANT**. Данные в **VARIANT**s могут храниться во многих форматах.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Обертка для типа автоматизации OLE **CURRENCY**, арифметического типа с фиксированной точкой, с 15 цифрами до десятичной точки и 4 цифрами после.

> [!NOTE]
> `CRect`, `CSize`, `CPoint` и могут быть пригодны для удовольствий в приложениях ATL или MFC. Кроме того, `CStringT` предоставляет MFC-независимый-подобный `CString`класс. Для получения дополнительной информации об общих классах утилиты [см.](../atl-mfc-shared/atl-mfc-shared-classes.md)

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../mfc/class-library-overview.md)
