---
title: Управление памятью с CStringT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b65efd934fecdab36bfa1c0c882de1dd8862c81f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="memory-management-with-cstringt"></a>Управление памятью с CStringT
Класс [CStringT](../atl-mfc-shared/reference/cstringt-class.md) — это класс шаблона, используемый для работы с переменной длиной символьных строк. Выпущена через диспетчер строковый объект, связанный с каждым экземпляром и выделения памяти для хранения этих строк `CStringT`. MFC и ATL предоставляют экземпляров по умолчанию `CStringT`, который называется `CString`, `CStringA`, и `CStringW`, который работы со строками из различных типов знаков. Эти типы символов имеют тип **TCHAR**, `char`, и `wchar_t`соответственно. Такие типы строк по умолчанию использовать диспетчер строки, который выделяет память из кучи процесса (в ATL) или кучу CRT (в MFC). Эта схема выделения памяти достаточно для типичных приложений. Однако для кода, выполняющего служб с интенсивными вычислениями используйте строки (или многопоточного кода), диспетчеры памяти по умолчанию может работать медленнее, чем. Описывается, как переопределить поведение по умолчанию памяти управления `CStringT`, создание Распределители специально оптимизированных для поставленной задачи.  
  
-   [Реализация пользовательского диспетчера строк (базовый метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Избежание состязания за кучу](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Реализация пользовательского диспетчера строк (расширенный метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: Пример пользовательского диспетчера строки](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>См. также  
 [Образце CustomString](../visual-cpp-samples.md)

