---
title: Классы для управления памятью (ATL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, managing
ms.assetid: be564a5e-577e-40a7-bfe3-25ad21e57270
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9cb6b0f75316f8c3a766ace94f6fd57c720aed
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757657"
---
# <a name="memory-management-classes"></a>Классы для управления памятью

Эти классы обеспечивают поддержку для кучи указатели, интеллектуальные указатели и других подпрограмм выделения памяти.

- [CAutoPtr](../atl/reference/cautoptr-class.md) этот класс представляет объект интеллектуального указателя.

- [CAutoPtrArray](../atl/reference/cautoptrarray-class.md) этот класс предоставляет методы, используемые при создании массива интеллектуальных указателей.

- [CAutoPtrList](../atl/reference/cautoptrlist-class.md) этот класс предоставляет методы, используемые при построении списка интеллектуальные указатели.

- [CAutoVectorPtr](../atl/reference/cautovectorptr-class.md) этот класс представляет объект интеллектуального указателя с помощью вектор new и delete операторов.

- [CComAllocator](../atl/reference/ccomallocator-class.md) этот класс предоставляет методы для управления памяти с помощью COM памяти подпрограммы.

- [CComGITPtr](../atl/reference/ccomgitptr-class.md) этот класс предоставляет методы для работы с указатели интерфейса и глобальной таблицы интерфейсов (GIT).

- [CComHeap](../atl/reference/ccomheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функции выделения памяти COM.

- [CComHeapPtr](../atl/reference/ccomheapptr-class.md) класс смарт-указатель для управления кучей указателей.

- [CComPtr](../atl/reference/ccomptr-class.md) класс смарт-указатель для управления указателей интерфейса СОМ.

- [CComPtrBase](../atl/reference/ccomptrbase-class.md) этот класс предоставляет основу для классов интеллектуальных указателей, использование памяти на основе COM-подпрограммы.

- [CComQIPtr](../atl/reference/ccomqiptr-class.md) класс смарт-указатель для управления указателей интерфейса СОМ.

- [CCRTAllocator](../atl/reference/ccrtallocator-class.md) этот класс предоставляет методы для управления памяти с помощью подпрограммы CRT памяти.

- [CCRTHeap](../atl/reference/ccrtheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функции кучи CRT.

- [CGlobalHeap](../atl/reference/cglobalheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функции глобального кучи Win32.

- [CHandle](../atl/reference/chandle-class.md) этот класс предоставляет методы для создания и использования объекта дескриптора.

- [CHeapPtr](../atl/reference/cheapptr-class.md) класс смарт-указатель для управления кучей указателей.

- [CHeapPtrBase](../atl/reference/cheapptrbase-class.md) этот класс — это основа для нескольких смарт-указатель классы кучи.

- [CHeapPtrList](../atl/reference/cheapptrlist-class.md) этот класс предоставляет методы, используемые при построении списка указатели кучи.

- [CLocalHeap](../atl/reference/clocalheap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функций Win32 локальной куче.

- [CWin32Heap](../atl/reference/cwin32heap-class.md) этот класс реализует [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.

- [IAtlMemMgr](../atl/reference/iatlmemmgr-class.md) этот класс представляет интерфейс для диспетчера памяти.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)

