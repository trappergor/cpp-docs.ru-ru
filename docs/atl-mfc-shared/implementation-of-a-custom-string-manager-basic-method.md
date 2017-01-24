---
title: "Implementation of a Custom String Manager (Basic Method) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class, использование"
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementation of a Custom String Manager (Basic Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Самый простой способ настройки схема выделения памяти для строковых данных использовать библиотеку ATL\-, класс **CAtlStringMgr** но предоставляет собственные процедуры выделения памяти.  Конструктор для **CAtlStringMgr** принимает один параметр: указатель на объект `IAtlMemMgr`.  `IAtlMemMgr` абстрактный базовый класс, который предоставляет универсальный интерфейс куча.  С помощью интерфейса `IAtlMemMgr`, **CAtlStringMgr**, reallocates и освобождает память, используемая для хранения сведений строки.  Самостоятельно любой реализовать интерфейс `IAtlMemMgr` или использовать одно из 5 библиотеки ATL\-, классы диспетчера памяти.  Библиотека ATL\-, средства выделения памяти для использования программы\-оболочек просто существующие диспетчеры памяти:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) Создает программу\-оболочку стандартные функции кучи CRT \([malloc](../c-runtime-library/reference/malloc.md), [free](../c-runtime-library/reference/free.md) и [realloc](../c-runtime-library/reference/realloc.md)\)  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) Создает дескриптор Win32 программу\-оболочку кучи, с помощью [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701) и [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Создает программу\-оболочку API Win32: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) и [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Создает программу\-оболочку API Win32: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) и [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) Создает программу\-оболочку API распределитель задачи модели COM. [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) и [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Для управления памятью строки самый удобный класс `CWin32Heap`, поскольку он позволяет создать кучи, независимо от числа, кратного.  Например, если нужно использовать отдельные кучу для строк, можно сделать следующее:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Для использования этого закрытого диспетчера строки управление памятью для переменной `CString`, передайте указатель на него в качестве параметра конструктору переменной `CString`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## См. также  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)