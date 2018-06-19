---
title: Реализация пользовательских строка Manager (базовый метод) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 259f9533747b266f0be0a782cdc94c98f167d2d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355729"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Реализация пользовательских строка Manager (базовый метод)
Самый простой способ настроить схему распределения памяти для строки данных является использование ATL предоставленной **CAtlStringMgr** класса, но также предоставить собственную памяти процедур выделения. Конструктор для **CAtlStringMgr** принимает один параметр: указатель на `IAtlMemMgr` объект. `IAtlMemMgr` Представляет абстрактный базовый класс, который предоставляет универсальный интерфейс к куче. С помощью `IAtlMemMgr` интерфейс, **CAtlStringMgr** выделяет, повторно выделяет и освобождает память, используемая для хранения строковых данных. Можно либо реализовать `IAtlMemMgr` интерфейс самостоятельно или использовать один из пяти классов диспетчер памяти ATL-условии. Диспетчеры памяти, предоставленный для ATL просто перенести существующие возможности выделения памяти:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) создает оболочку для стандартных функций кучи CRT ([malloc](../c-runtime-library/reference/malloc.md), [свободного](../c-runtime-library/reference/free.md), и [realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) переносит обработки кучи Win32, с помощью [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), и [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) создает оболочку для API-интерфейсов Win32: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), и [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) создает оболочку для API-интерфейсов Win32: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), и [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) создает оболочку для API-интерфейсы COM задач распределителя: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), и [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 С целью управления памятью строки, наиболее полезные класс является `CWin32Heap` , так как оно дает возможность создания нескольких независимых куч. Например если вы хотели использовать отдельной куче только для строк, может необходимо следующее:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Для использования этого диспетчера частную строковую управление памятью для `CString` переменной, передайте значение указателя к диспетчеру как параметр `CString` конструктор переменной:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Управление памятью с помощью CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

