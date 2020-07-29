---
title: Управление памятью с помощью CStringT
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: bf1f99b92761c84d59b6f7bfb9aef67d7e097893
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222034"
---
# <a name="memory-management-with-cstringt"></a>Управление памятью с помощью CStringT

Класс [CStringT](../atl-mfc-shared/reference/cstringt-class.md) — это класс шаблона, используемый для управления символьными строками переменной длины. Память для хранения этих строк выделяется и освобождается через объект диспетчера строк, связанный с каждым экземпляром `CStringT` . MFC и ATL предоставляют экземпляры по умолчанию `CStringT` , называемые `CString` , `CStringA` и `CStringW` , которые управляют строками различных символьных типов. Эти типы символов имеют тип TCHAR, **`char`** и **`wchar_t`** соответственно. Эти строковые типы по умолчанию используют диспетчер строк, который выделяет память из кучи процесса (в ATL) или кучи CRT (в MFC). Для типичных приложений эта схема выделения памяти достаточно велика. Однако для кода, выполняющего интенсивное использование строк (или многопоточного кода), стандартные диспетчеры памяти могут работать не оптимально. В этом разделе описывается, как переопределить поведение управления памятью по умолчанию для `CStringT` , создавая распределителя, специально оптимизированные для поставленной задачи.

- [Реализация пользовательского диспетчера строк (базовый метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Избежание конфликтов кучи](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Реализация пользовательского диспетчера строк (Расширенный метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: пример пользовательского диспетчера строк](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>См. также раздел

[Пример Кустомстринг](../overview/visual-cpp-samples.md)
