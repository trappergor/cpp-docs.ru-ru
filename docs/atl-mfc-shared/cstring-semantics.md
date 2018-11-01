---
title: Семантика CString
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: f563b24a9df61a91711433a4e4987f8f800545ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657799"
---
# <a name="cstring-semantics"></a>Семантика CString

Несмотря на то что [CString](../atl-mfc-shared/reference/cstringt-class.md) объектов, динамические объекты, которые может увеличиваться, они действуют как встроенные типы-примитивы и простые классы. Каждый `CString` объект представляет уникальное значение. `CString` объекты должны рассматриваться как фактические строки, а не как указатели на строки.

Можно назначить одно `CString` объект с другим объектом. Тем не менее, при изменении одного из двух `CString` объектов, другой `CString` объекта не изменяется, как показано в следующем примере:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Обратите внимание, в примере, два `CString` объекты считаются «equal», так как они представляют одну и ту же строку символов. `CString` Класс перегружает оператор равенства (`==`) для сравнения двух `CString` объекты на основе их значения (содержимое) вместо учетных данных (адрес).

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

