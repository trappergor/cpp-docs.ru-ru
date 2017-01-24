---
title: "Memory Management with CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, description of"
  - "CString objects, управление памятью"
  - "CStringT class, управление памятью"
  - "IAtlStringMgr class, использование"
  - "память [C++], использования"
  - "строки [C++], custom memory management"
  - "строки [C++], управление памятью"
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Memory Management with CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс [CStringT](../atl-mfc-shared/reference/cstringt-class.md) является классом шаблона, используемый для обработки символьной строки переменной длины.  Память для хранения этих строк выделена и освобождатьа через объект диспетчера строк, связанный с каждым экземпляром `CStringT`.  MFC и библиотеки ATL предоставляют по умолчанию, вызываемые экземпляров `CStringT`, `CString`, `CStringA` и `CStringW`, которые обрабатывают строки различных типов символов.  Эти типы символов типа **TCHAR**, `char` и `wchar_t` соответственно.  По умолчанию эти строковые типы используют диспетчер строки, который выделяет память из кучи \(процесса в библиотеку ATL\) или кучи CRT \(в MFC\).  Для типичных приложений эта схема выделения памяти недостаточно.  Однако для кода при интенсивнейшую использование строк \(или многопоточный код\) по умолчанию диспетчеры памяти не могут работать оптимально.  В этом подразделе описывается, как переопределить используемый по умолчанию применяются расширения функциональности управления памятью `CStringT` создать allocators в частности, оптимизированные для задачи в рамках передать края.  
  
-   [Реализация пользовательского диспетчера строки \(базовый метод\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Избегание конфликтах кучи](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Реализация пользовательского диспетчера строки \(расширенный метод\)](../Topic/Implementation%20of%20a%20Custom%20String%20Manager%20\(Advanced%20Method\).md)  
  
-   [CFixedStringT: Пример пользовательского диспетчера строки](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## См. также  
 [Образец CustomString](../top/visual-cpp-samples.md)