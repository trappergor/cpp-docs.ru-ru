---
title: Классы коллекций ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- collection classes
ms.assetid: eff95de6-78ef-4212-9d7d-1dacbdd4cc58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5cc94c2b935198cd3c445e8460e23ebbf2af55b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752672"
---
# <a name="collection-classes"></a>Классы коллекций

Следующие классы поддерживают массивы, списки, карт, а также методы признаки для оказания помощи сравнения и доступ к элементам.

- [CAtlArray](../atl/reference/catlarray-class.md) этот класс реализует объект массива.

- [CAtlList](../atl/reference/catllist-class.md) этот класс предоставляет методы для создания и управления объект списка.

- [CAtlMap](../atl/reference/catlmap-class.md) этот класс предоставляет методы для создания и управления объект карты.

- [CAutoPtrArray](../atl/reference/cautoptrarray-class.md) этот класс предоставляет методы, используемые при создании массива интеллектуальных указателей.

- [CAutoPtrElementTraits](../atl/reference/cautoptrelementtraits-class.md) этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекции интеллектуальных указателей.

- [CAutoPtrList](../atl/reference/cautoptrlist-class.md) этот класс предоставляет методы, используемые при построении списка интеллектуальные указатели.

- [CAutoVectorPtrElementTraits](../atl/reference/cautovectorptrelementtraits-class.md) этот класс предоставляет методы, статические функции и определения типов, полезных при создании коллекции с помощью интеллектуальных указателей, новые векторные и удаление операторов.

- [CComQIPtrElementTraits](../atl/reference/ccomqiptrelementtraits-class.md) этот класс предоставляет методы, статические функции и определения типов, полезных при создании коллекции COM указателей на интерфейс.

- [CComSafeArray](../atl/reference/ccomsafearray-class.md) этот класс является оболочкой для [SAFEARRAY Data Type](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray) структуры.

- [CComSafeArrayBound](../atl/reference/ccomsafearraybound-class.md) этот класс является оболочкой для [SAFEARRAYBOUND](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearraybound) структуры.

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) в этом классе хранится **IUnknown** указатели и предназначен для использования в качестве параметра [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) класс шаблона.

- [CDefaultCharTraits](../atl/reference/cdefaultchartraits-class.md) этот класс предоставляет два статических функций для преобразования символов в верхний или нижний регистр.

- [CDefaultCompareTraits](../atl/reference/cdefaultcomparetraits-class.md) этого класса предоставляют функции сравнения элемент по умолчанию.

- [CDefaultElementTraits](../atl/reference/cdefaultelementtraits-class.md) этот класс предоставляет функции и методы по умолчанию для класса коллекции.

- [CDefaultHashTraits](../atl/reference/cdefaulthashtraits-class.md) этот класс предоставляет статическую функцию для вычисления хэш-значения.

- [CElementTraits](../atl/reference/celementtraits-class.md) этот класс используется классами коллекцию для предоставления методов и функций для перемещения, копирования, сравнения и операциях хеширования.

- [CElementTraitsBase](../atl/reference/celementtraitsbase-class.md) этот класс предоставляет по умолчанию методы копирования и перемещения для класса коллекции.

- [CHeapPtrElementTraits](../atl/reference/cheapptrelementtraits-class.md) этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекций указателей кучи.

- [CHeapPtrList](../atl/reference/cheapptrlist-class.md) этот класс предоставляет методы, используемые при построении списка указатели кучи.

- [CInterfaceArray](../atl/reference/cinterfacearray-class.md) этот класс предоставляет методы, используемые при создании массива указателей COM-интерфейса.

- [CInterfaceList](../atl/reference/cinterfacelist-class.md) этот класс предоставляет методы, используемые при построении списка указателей интерфейса СОМ.

- [CPrimitiveElementTraits](../atl/reference/cprimitiveelementtraits-class.md) этот класс предоставляет методы по умолчанию, а также функции для класса коллекции состоят из примитивных типов данных.

- [CRBMap](../atl/reference/crbmap-class.md) этот класс представляет структуру сопоставления, с помощью двоичного красно-черного дерева.

- [CRBMultiMap](../atl/reference/crbmultimap-class.md) этот класс представляет структуру сопоставления, которая позволяет каждого ключа должны быть сопоставлены более одного значения, с помощью двоичного красно-черного дерева.

- [CRBTree](../atl/reference/crbtree-class.md) этот класс предоставляет методы для создания и использования красно-черного дерева.

- [CSimpleArray](../atl/reference/csimplearray-class.md) этот класс предоставляет методы для управления простого массива.

- [CSimpleArrayEqualHelper](../atl/reference/csimplearrayequalhelper-class.md) этот класс представляет вспомогательный объект для [CSimpleArray](../atl/reference/csimplearray-class.md) класса.

- [CSimpleArrayEqualHelperFalse](../atl/reference/csimplearrayequalhelperfalse-class.md) этот класс представляет вспомогательный объект для [CSimpleArray](../atl/reference/csimplearray-class.md) класса.

- [CSimpleMap](../atl/reference/csimplemap-class.md) этот класс обеспечивает поддержку для массива простое сопоставление.

- [CSimpleMapEqualHelper](../atl/reference/csimplemapequalhelper-class.md) этот класс представляет вспомогательный объект для [CSimpleMap](../atl/reference/csimplemap-class.md) класса.

- [CSimpleMapEqualHelperFalse](../atl/reference/csimplemapequalhelperfalse-class.md) этот класс представляет вспомогательный объект для [CSimpleMap](../atl/reference/csimplemap-class.md) класса.

- [CStringElementTraits](../atl/reference/cstringelementtraits-class.md) этот класс предоставляет статические функции, используемые классами коллекцию хранения `CString` объектов.

- [CStringElementTraitsI](../atl/reference/cstringelementtraitsi-class.md) этот класс предоставляет статические функции, связанные с строк, которые хранятся в объектах класса коллекции. Это похоже на [CStringElementTraits](../atl/reference/cstringelementtraits-class.md), но выполняет сравнение без учета регистра.

- [CStringRefElementTraits](../atl/reference/cstringrefelementtraits-class.md) этот класс предоставляет статические функции, связанные с строк, которые хранятся в объектах класса коллекции. Объекты-строки обрабатываются как ссылки.

## <a name="related-articles"></a>Связанные статьи

[Классы коллекций ATL](../atl/atl-collection-classes.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)   
[Классы коллекций](../atl/atl-collection-classes.md)

