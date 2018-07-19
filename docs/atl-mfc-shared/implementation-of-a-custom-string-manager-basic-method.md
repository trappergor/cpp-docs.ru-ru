---
title: Реализация из пользовательского диспетчера строк (базовый метод) | Документация Майкрософт
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
ms.openlocfilehash: c393489b8b4d0353ae37a21132f66e0618b3b794
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884588"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Реализация из пользовательского диспетчера строк (базовый метод)
Самый простой способ настроить схемы выделения памяти для строковых данных является использование предоставляемых ATL `CAtlStringMgr` класса, но предоставляют свои собственные памяти процедур выделения. Конструктор для `CAtlStringMgr` принимает один параметр: указатель на `IAtlMemMgr` объект. `IAtlMemMgr` — Это абстрактный базовый класс, который предоставляет универсальный интерфейс в кучу. С помощью `IAtlMemMgr` интерфейс, `CAtlStringMgr` выделяет, повторно выделяет и освобождает память, используемую для хранения строковых данных. Можно либо реализовать `IAtlMemMgr` интерфейс самостоятельно или использовать один из пяти manager классов ATL предоставляемой памяти. Диспетчеры ATL предоставляемой памяти просто перенести существующие средства выделения памяти:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) создает оболочку для стандартных функций кучи CRT ([malloc](../c-runtime-library/reference/malloc.md), [бесплатный](../c-runtime-library/reference/free.md), и [realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) переносит обрабатывать кучи Win32, с помощью [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), и [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) создает оболочку для API-интерфейсов Win32: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), и [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) создает оболочку для API-интерфейсов Win32: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), и [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) создает оболочку для API-интерфейсы распределителя COM-задач: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), и [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Для целей строка управление памятью, наиболее полезных класс является `CWin32Heap` , так как он позволяет создавать несколько независимых куч. Например если вы хотите использовать отдельной куче только для строк, удалось сделайте следующее:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Чтобы использовать этот диспетчер закрытую строковую для управления памятью для `CString` переменной, передайте указатель этот диспетчер в качестве параметра `CString` конструктор переменной:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Управление памятью с помощью CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

