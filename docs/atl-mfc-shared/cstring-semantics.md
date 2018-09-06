---
title: Семантика CString | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 256c71cace15a3906ac048819ab2ffdef2071ff4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761277"
---
# <a name="cstring-semantics"></a>Семантика CString

Несмотря на то что [CString](../atl-mfc-shared/reference/cstringt-class.md) объектов, динамические объекты, которые может увеличиваться, они действуют как встроенные типы-примитивы и простые классы. Каждый `CString` объект представляет уникальное значение. `CString` объекты должны рассматриваться как фактические строки, а не как указатели на строки.

Можно назначить одно `CString` объект с другим объектом. Тем не менее, при изменении одного из двух `CString` объектов, другой `CString` объекта не изменяется, как показано в следующем примере:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Обратите внимание, в примере, два `CString` объекты считаются «equal», так как они представляют одну и ту же строку символов. `CString` Класс перегружает оператор равенства (`==`) для сравнения двух `CString` объекты на основе их значения (содержимое) вместо учетных данных (адрес).

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

