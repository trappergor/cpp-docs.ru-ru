---
title: Семантика CString | Документы Microsoft
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
ms.openlocfilehash: b1765f1f7f4103b1b2cfe6012b42ebef12f8863f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cstring-semantics"></a>Семантика CString
Несмотря на то что [CString](../atl-mfc-shared/reference/cstringt-class.md) объекты являются динамические, может увеличиваться, они действуют как простые классы и встроенные типы-примитивы. Каждый `CString` объект представляет уникальное значение. `CString` объекты следует рассматривать как фактические строки, а не как указатели на строки.  
  
 Можно назначить один **CString** объекта в другой. Тем не менее, при изменении одного из двух `CString` объектов, другой `CString` объекта не изменяется, как показано в следующем примере:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]  
  
 Обратите внимание, в примере, два `CString` объекты считаются «равно», так как они представляют одну и ту же строку символов. `CString` Класс перегружает оператор равенства (`==`) для сравнения двух `CString` объекты на основе их значения (содержимое) вместо учетных данных (адрес).  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)

